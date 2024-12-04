# API Integration Examples

## REST API Operations

### GET Request with Authentication
```powershell
# Set up authentication
Variables.SetVariable Headers: {
    "Authorization": "Bearer " + %ApiToken%,
    "Content-Type": "application/json",
    "Accept": "application/json"
}

# Make API request
Web.InvokeWebService.InvokeWebService 
    Url: "https://api.example.com/data" 
    Method: Web.Method.Get 
    CustomHeaders: %Headers% 
    ConnectionTimeout: 30 
    FollowRedirection: True 
    Response=> ApiResponse

# Parse response
Variables.ConvertJsonToCustomObject 
    Json: %ApiResponse% 
    CustomObject=> ResponseData

# Process data
LOOP FOREACH Item IN %ResponseData.items%
    # Process each item
    ProcessApiItem Item: %Item%
END LOOP
```

### POST Request with Error Handling
```powershell
# Prepare request body
Variables.SetVariable RequestBody: {
    "name": %CustomerName%,
    "email": %CustomerEmail%,
    "status": "active"
}

Variables.ConvertCustomObjectToJson 
    CustomObject: %RequestBody% 
    Json=> JsonBody

# Make API request with error handling
BLOCK "API Request"
ON BLOCK ERROR
    # Log error
    System.LogMessage "API Error: %LastError%"
    
    # Retry logic
    IF RetryCount < MaxRetries THEN
        Variables.IncreaseVariable Value: %RetryCount% IncrementValue: 1
        System.Wait Seconds: 5
        GOTO "RetryRequest"
    END
END
    LABEL "RetryRequest"
    Web.InvokeWebService.InvokeWebService 
        Url: "https://api.example.com/customers" 
        Method: Web.Method.Post 
        ContentType: "application/json" 
        RequestBody: %JsonBody% 
        ConnectionTimeout: 30 
        Response=> ApiResponse
        StatusCode=> StatusCode
    
    # Check response
    IF StatusCode >= 400 THEN
        THROW "API Error: " + %ApiResponse%
    END
END
```

### Batch Processing with API
```powershell
# Initialize batch
Variables.SetVariable BatchSize: 100
Variables.SetVariable CurrentBatch: []

# Process items in batches
LOOP FOREACH Item IN %LargeDataset%
    # Add to current batch
    List.AddItem List: %CurrentBatch% Item: %Item%
    
    # Process batch when full
    IF List.Count(%CurrentBatch%) >= BatchSize THEN
        # Convert batch to JSON
        Variables.ConvertCustomObjectToJson 
            CustomObject: %CurrentBatch% 
            Json=> BatchJson
        
        # Send batch to API
        Web.InvokeWebService.InvokeWebService 
            Url: "https://api.example.com/batch" 
            Method: Web.Method.Post 
            ContentType: "application/json" 
            RequestBody: %BatchJson% 
            Response=> BatchResponse
        
        # Clear batch
        Variables.SetVariable CurrentBatch: []
    END
END LOOP
```