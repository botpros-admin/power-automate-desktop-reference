# Advanced Automation Patterns

## 1. State Machine Pattern

### Implementation
```powershell
# Define states
Variables.SetVariable States: {
    "New": "ProcessNew",
    "Pending": "ProcessPending",
    "Review": "ProcessReview",
    "Complete": "ProcessComplete",
    "Error": "HandleError"
}

# State machine function
SUBFLOW "ProcessStateMachine"
INPUT CurrentState, ItemData
OUTPUT NextState
    # Get handler for current state
    Variables.SetVariable StateHandler: %States[CurrentState]%
    
    # Execute state handler
    BLOCK "Execute State"
    ON BLOCK ERROR
        Variables.SetVariable NextState: "Error"
        THROW ERROR
    END
        CALL FUNCTION %StateHandler%
            INPUT: %ItemData%
            OUTPUT: StateResult
        
        # Determine next state
        Variables.SetVariable NextState: %StateResult.NextState%
    END
END SUBFLOW
```

## 2. Pipeline Pattern

### Implementation
```powershell
# Define pipeline stages
Variables.SetVariable PipelineStages: [
    "Validate",
    "Transform",
    "Enrich",
    "Process",
    "Archive"
]

# Pipeline processor
SUBFLOW "ProcessPipeline"
INPUT Data
OUTPUT ProcessedData
    Variables.SetVariable CurrentData: %Data%
    
    # Process each stage
    LOOP FOREACH Stage IN %PipelineStages%
        BLOCK "Pipeline Stage"
        ON BLOCK ERROR
            System.LogMessage "Error in stage: %Stage%"
            THROW ERROR
        END
            # Execute stage
            CALL FUNCTION "Process" + %Stage%
                INPUT: %CurrentData%
                OUTPUT: StageResult
            
            # Update data for next stage
            Variables.SetVariable CurrentData: %StageResult%
        END
    END LOOP
    
    # Return final result
    Variables.SetVariable ProcessedData: %CurrentData%
END SUBFLOW
```

## 3. Observer Pattern

### Implementation
```powershell
# Define observers
Variables.SetVariable Observers: {
    "FileCreated": [
        "LogFileCreation",
        "NotifyAdmin",
        "ProcessNewFile"
    ],
    "ProcessComplete": [
        "UpdateDatabase",
        "SendNotification",
        "ArchiveFile"
    ]
}

# Notify observers
SUBFLOW "NotifyObservers"
INPUT EventType, EventData
    # Get observers for event
    Variables.SetVariable EventObservers: %Observers[EventType]%
    
    # Notify each observer
    LOOP FOREACH Observer IN %EventObservers%
        BLOCK "Notify Observer"
        ON BLOCK ERROR
            System.LogMessage "Error notifying observer: %Observer%"
            NEXT LOOP
        END
            CALL FUNCTION %Observer%
                INPUT: %EventData%
        END
    END LOOP
END SUBFLOW
```

## 4. Retry Pattern with Exponential Backoff

### Implementation
```powershell
# Retry with exponential backoff
SUBFLOW "RetryOperation"
INPUT Operation, MaxRetries
    Variables.SetVariable RetryCount: 0
    Variables.SetVariable BaseDelay: 2  # seconds
    
    LABEL "RetryAttempt"
    BLOCK "Execute Operation"
    ON BLOCK ERROR
        # Check retry count
        IF RetryCount < MaxRetries THEN
            # Calculate delay
            Variables.SetVariable Delay: 
                Math.Power(%BaseDelay%, %RetryCount%)
            
            # Log retry
            System.LogMessage 
                "Retry %RetryCount% after %Delay% seconds"
            
            # Wait and retry
            System.Wait Seconds: %Delay%
            Variables.IncreaseVariable 
                Value: %RetryCount% 
                IncrementValue: 1
            GOTO "RetryAttempt"
        ELSE
            THROW "Max retries exceeded"
        END
    END
        # Execute operation
        CALL FUNCTION %Operation%
    END
END SUBFLOW
```