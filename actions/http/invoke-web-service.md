# Invoke Web Service

## Description
Invokes a web service by sending data and retrieves the response.

## Syntax
```
Web.InvokeWebService.InvokeWebService Url: `[url]` Method: Web.Method.Get Accept: $'''application/xml''' ContentType: $'''application/xml''' ConnectionTimeout: 30 FollowRedirection: True ClearCookies: False FailOnErrorStatus: False EncodeRequestBody: True UserAgent: $'''Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.8.1.21) Gecko/20100312 Firefox/3.6''' Encoding: Web.Encoding.AutoDetect AcceptUntrustedCertificates: False TrimRequestBody: True ResponseHeaders=> WebServiceResponseHeaders Response=> WebServiceResponse StatusCode=> StatusCode
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| URL | Yes | Text value | - | The web service's URL |
| Method | Yes | GET, POST, PUT, DELETE, etc. | GET | The HTTP method to use |
| Accept | No | Text value | application/xml | Acceptable content type for response |
| Content type | No | Text value | application/xml | Content type of the request |
| Custom headers | No | Text value | - | Custom headers for the request |
| Request body | No | Text value | - | Body of the request |
| Connection timeout | No | Numeric value | 30 | Time in seconds to wait for connection |
| Follow redirection | No | Boolean value | True | Allow redirects |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| WebServiceResponseHeaders | List of Text values | HTTP headers of the response |
| WebServiceResponse | Text value | Web service response text |
| StatusCode | Numeric value | HTTP status code |

## Example Usage

### OpenAI API Call
```
Web.InvokeWebService.InvokeWebService \
    Url: $'''https://api.openai.com/v1/chat/completions''' \
    Method: Web.Method.Post \
    Accept: $'''application/json''' \
    ContentType: $'''application/json''' \
    CustomHeaders: $'''Authorization: Bearer [your-token]''' \
    RequestBody: $'''{"model": "gpt-4o-mini",
        "messages": [
            {"role": "system", "content": "[system prompt]"},
            {"role": "user", "content": "%FileContents%"}
        ],
        "temperature": 0.1
    }''' \
    EncodeRequestBody: False \
    Response=> apiResponse
```

### Basic GET Request
```
Web.InvokeWebService.InvokeWebService \
    Url: $'''https://api.example.com/data''' \
    Method: Web.Method.Get \
    Accept: $'''application/json''' \
    Response=> responseData
```

## Best Practices
1. Always set appropriate timeouts
2. Handle status codes appropriately
3. Use EncodeRequestBody: False for pre-formatted JSON
4. Include proper content type headers