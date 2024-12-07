# Download from Web

## Description
Downloads text or a file from the web and stores it.

## Syntax
```
Web.DownloadFromWeb.Download Url: `[url]` ConnectionTimeout: 30 FollowRedirection: True ClearCookies: False UserAgent: $'''Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.8.1.21) Gecko/20100312 Firefox/3.6''' Encoding: Web.Encoding.AutoDetect AcceptUntrustedCertificates: False WebPageText=> WebPageText
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| URL | Yes | Text value | - | The web page or file's URL |
| Method | Yes | GET, POST | GET | Specify how to retrieve website information |
| Post parameters | Yes (if POST) | Datatable | - | The POST parameters in the form of a datatable with two columns |
| Save response | No | Get text into variable (for web pages), Save to disk (for files) | Get text into variable | Specify how the returned data will be saved |
| File name | No | Keep original file name, Specify full path | Keep original | Specify whether to keep original file name or specify new name |
| Connection timeout | No | Numeric value | 30 | The time in seconds to wait for connection |
| Follow redirection | No | Boolean value | True | Allow web server redirection |
| Clear cookies | No | Boolean value | False | Clear all cookies from similar actions |
| User agent | No | Text value | Mozilla/5.0... | Browser identity to use |
| Encoding | No | [List of encodings] | Auto - detect | The encoding for the web page |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| DownloadedFile | File | The downloaded file |
| WebPageText | Text value | The web page text |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Directory doesn't exist | Required directory not found |
| Download from web error | Problem downloading from web |

## Known Issues
- NTLM Authentication is not supported for web requests

## Example Usage

### Basic Download
```
Web.DownloadFromWeb.Download Url: $'''https://example.com/file.pdf''' WebPageText=> WebPageText
```

### Download with Custom Settings
```
Web.DownloadFromWeb.Download \
    Url: $'''https://api.example.com/data''' \
    ConnectionTimeout: 60 \
    FollowRedirection: True \
    ClearCookies: True \
    UserAgent: $'''Custom User Agent''' \
    Encoding: Web.Encoding.UTF8 \
    WebPageText=> ResponseData
```