# Power Automate Desktop Design Patterns

## 1. Retry Pattern

### Basic Retry
```powershell
Variables.SetVariable RetryCount: 0
Variables.SetVariable MaxRetries: 3

LABEL "RetryOperation"
BLOCK "Operation"
ON BLOCK ERROR
    Variables.IncreaseVariable Value: %RetryCount% IncrementValue: 1
    IF RetryCount < MaxRetries THEN
        System.Wait Seconds: 5
        GOTO "RetryOperation"
    ELSE
        THROW ERROR
    END
END
    # Main operation
END
```

## 2. Facade Pattern

### Simplified Interface
```powershell
SUBFLOW "ProcessCustomer"
INPUT CustomerId
    # Complex operations hidden behind simple interface
    BLOCK "Customer Processing"
    ON BLOCK ERROR
        HandleCustomerError CustomerId: %CustomerId%
    END
        ValidateCustomer CustomerId: %CustomerId%
        UpdateCustomerRecords CustomerId: %CustomerId%
        NotifyCustomer CustomerId: %CustomerId%
    END
END SUBFLOW
```

## 3. Factory Pattern

### Object Creation
```powershell
SUBFLOW "CreateCustomerRecord"
INPUT CustomerType, CustomerData
    BLOCK "Record Creation"
    ON BLOCK ERROR
        THROW ERROR
    END
        # Create appropriate customer record based on type
        IF CustomerType = "Corporate" THEN
            CreateCorporateCustomer Data: %CustomerData%
        ELSE IF CustomerType = "Individual" THEN
            CreateIndividualCustomer Data: %CustomerData%
        END
    END
END SUBFLOW
```

## 4. Observer Pattern

### Event Handling
```powershell
SUBFLOW "NotifyObservers"
INPUT EventType, EventData
    # Notify all registered observers
    LOOP FOREACH Observer IN %RegisteredObservers%
        IF Observer.EventTypes CONTAINS EventType THEN
            NotifyObserver Observer: %Observer% EventData: %EventData%
        END
    END LOOP
END SUBFLOW
```

## 5. State Pattern

### State Management
```powershell
SUBFLOW "ProcessOrderState"
INPUT Order
    # Handle order based on current state
    SWITCH Order.State
        CASE "New"
            ProcessNewOrder Order: %Order%
        CASE "Pending"
            ProcessPendingOrder Order: %Order%
        CASE "Complete"
            ProcessCompletedOrder Order: %Order%
        DEFAULT
            HandleInvalidState Order: %Order%
    END SWITCH
END SUBFLOW
```