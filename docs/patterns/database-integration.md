# Database Integration Patterns

## 1. Batch Database Operations

### Batch Insert Pattern
```powershell
# Initialize batch processing
Variables.SetVariable BatchSize: 1000
Variables.SetVariable CurrentBatch: []

BLOCK "Database Operations"
ON BLOCK ERROR
    System.LogMessage "Database Error: %LastError%"
    # Implement rollback if needed
END
    # Connect to database
    Database.Connect 
        ConnectionString: %Config.DatabaseConnection% 
        Connection=> DBConnection
    
    # Process records in batches
    LOOP FOREACH Record IN %DataToProcess%
        # Add to current batch
        List.AddItem List: %CurrentBatch% Item: %Record%
        
        # Process batch when full
        IF List.Count(%CurrentBatch%) >= BatchSize THEN
            ProcessDatabaseBatch 
                Connection: %DBConnection% 
                BatchData: %CurrentBatch%
            
            # Clear batch
            Variables.SetVariable CurrentBatch: []
        END
    END LOOP
    
    # Process remaining records
    IF List.Count(%CurrentBatch%) > 0 THEN
        ProcessDatabaseBatch 
            Connection: %DBConnection% 
            BatchData: %CurrentBatch%
    END
    
    # Cleanup
    Database.Close Connection: %DBConnection%
END
```

## 2. Transaction Management

### Transaction Pattern
```powershell
SUBFLOW "ExecuteWithTransaction"
INPUT Operations
    BLOCK "Transaction Block"
    ON BLOCK ERROR
        # Rollback on error
        Database.ExecuteSqlStatement.Execute 
            Connection: %DBConnection% 
            Statement: "ROLLBACK;"
        THROW ERROR
    END
        # Begin transaction
        Database.ExecuteSqlStatement.Execute 
            Connection: %DBConnection% 
            Statement: "BEGIN TRANSACTION;"
        
        # Execute operations
        LOOP FOREACH Operation IN %Operations%
            Database.ExecuteSqlStatement.Execute 
                Connection: %DBConnection% 
                Statement: %Operation%
        END LOOP
        
        # Commit transaction
        Database.ExecuteSqlStatement.Execute 
            Connection: %DBConnection% 
            Statement: "COMMIT;"
    END
END SUBFLOW
```