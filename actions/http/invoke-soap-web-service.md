# Invoke SOAP Web Service

## Description
Invokes a method from a SOAP web service.

## Syntax
```
Web.InvokeSoapService.InvokeSoapService Endpoint: `[endpoint]` RequestBody: `[body]` ConnectionTimeout: 30 FollowRedirection: True ClearCookies: False FailOnErrorStatus: False UserAgent: $'''Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.8.1.21) Gecko/20100312 Firefox/3.6''' Encoding: Web.Encoding.AutoDetect AcceptUntrustedCertificates: False TrimRequestBody: True ResponseHeaders=> SoapServiceResponseHeaders Response=> SoapServiceResponse StatusCode=> StatusCode
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Endpoint | Yes | Text value | - | The endpoint of the web service |
| Custom headers | No | Text value | - | Custom headers for the request |
| Request body | Yes | Text value | - | The body of the request |
| Connection timeout | Yes | Numeric value | 30 | Time in seconds to wait for connection |
| Follow redirection | No | Boolean value | True | Allow redirects |
| Clear cookies | No | Boolean value | False | Clear cookies from previous actions |
| Fail on error status | No | Boolean value | False | Process error responses as normal |
| User agent | No | Text value | Mozilla/5.0... | Browser identity to use |
| Encoding | No | [List of encodings] | Auto - detect | Encoding for response |

## Request Builder Parameters

| Parameter | Accepts | Description |
|-----------|----------|-------------|
| WSDL | File | The WSDL document to build request |
| Service | Text value | The service to invoke |
| Port | Text value | The port to invoke the service |
| SOAP version | Text value | The version of SOAP service |
| Operation | Text value | The operation to invoke |
| Request envelope | Text value | The envelope for the request |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| SoapServiceResponseHeaders | List of Text values | HTTP headers of response |
| SoapServiceResponse | Text value | Web service response text |
| StatusCode | Numeric value | Status code returned |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Invoke SOAP service error | Problem invoking the service |
| Invalid header in custom headers | Invalid custom headers |

## Known Issues
- NTLM Authentication is not supported

## Example Usage

### Basic SOAP Request
```
Web.InvokeSoapService.InvokeSoapService \
    Endpoint: $'''http://example.com/soap''' \
    RequestBody: $'''<?xml version="1.0"?>
<soap:Envelope>
    <soap:Body>
        <GetStockPrice>
            <StockName>MSFT</StockName>
        </GetStockPrice>
    </soap:Body>
</soap:Envelope>''' \
    Response=> soapResponse
```

### SOAP Request with Custom Headers
```
Web.InvokeSoapService.InvokeSoapService \
    Endpoint: $'''http://api.example.com/soap''' \
    CustomHeaders: $'''SOAPAction: "http://example.com/GetPrice"
Authorization: Basic [token]''' \
    RequestBody: $'''[SOAP envelope]''' \
    FailOnErrorStatus: True \
    Response=> soapResponse
```

## Best Practices
1. Always specify SOAP action in headers when required
2. Handle response status codes appropriately
3. Set proper timeouts for long-running operations
4. Use appropriate error handling