# Vexoo API Documentation - 1.0.4
## Introduction

The Vexoo API provides advanced search capabilities using various language models and specialized search contexts. This documentation covers all aspects of interacting with the API, including available endpoints, request/response formats, and best practices.

**IMPORTANT**: This API is currently in Pre-Beta Version 1.0.4 and does not implement authorization. Users are responsible for maintaining the confidentiality of these endpoints and should not share access or documentation publicly.

## Base URL

All API requests should be made to the following base URL:

```
http://172.190.86.16:8000/docs#/
```

## Authentication

Currently, the API does not implement any authentication mechanism. Users should exercise caution and maintain the confidentiality of the API endpoints.

## Request Format

All API endpoints accept POST requests with a JSON payload. The general format of the request body is as follows:

```json
{
  "input": {
    "query": "Your search query here"
  }
}
```

- The `input` field is an object containing the search parameters.
- The `query` field within `input` contains the actual search query as a string.

## Response Format

The API returns streaming responses. This means that the data is sent in chunks as it becomes available, rather than waiting for the entire response to be ready before sending.

The exact format of each chunk may vary depending on the specific endpoint and the nature of the search performed. Generally, you can expect the response to be in plain text format, with each chunk containing a portion of the search results.

## Endpoints

### Vexoo Search Endpoints

#### Search Mistral

- **URL**: `/api/v1/SearchMistral`
- **Method**: POST
- **Description**: Performs a search using the Mistral language model

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/SearchMistral"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Latest advancements in quantum computing"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/SearchMistral" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Latest advancements in quantum computing\"}}"
```

#### Search Claude

- **URL**: `/api/v1/SearchClaude`
- **Method**: POST
- **Description**: Performs a search using the Claude language model

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/SearchClaude"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Explain the theory of relativity"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/SearchClaude" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Explain the theory of relativity\"}}"
```

#### Search Evidence

- **URL**: `/api/v1/SearchEvidence`
- **Method**: POST
- **Description**: Searches for evidence-based information

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/SearchEvidence"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Evidence for climate change"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/SearchEvidence" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Evidence for climate change\"}}"
```

### Scholar Search Endpoints

#### Scholar Search Mistral

- **URL**: `/api/v1/ScholarMistral`
- **Method**: POST
- **Description**: Performs an academic search using the Mistral model

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/ScholarMistral"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Recent developments in CRISPR technology"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/ScholarMistral" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Recent developments in CRISPR technology\"}}"
```

#### Scholar Search Claude

- **URL**: `/api/v1/ScholarClaude`
- **Method**: POST
- **Description**: Performs an academic search using the Claude model

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/ScholarClaude"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Advancements in artificial intelligence ethics"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/ScholarClaude" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Advancements in artificial intelligence ethics\"}}"
```

#### Scholar Search Evidence

- **URL**: `/api/v1/ScholarEvidence`
- **Method**: POST
- **Description**: Searches for evidence in academic contexts

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/ScholarEvidence"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Evidence for dark matter in the universe"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/ScholarEvidence" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Evidence for dark matter in the universe\"}}"
```

### News Search Endpoints

#### News Search Mistral

- **URL**: `/api/v1/NewsMistral`
- **Method**: POST
- **Description**: Performs a news search using the Mistral model

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/NewsMistral"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Latest developments in renewable energy"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/NewsMistral" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Latest developments in renewable energy\"}}"
```

#### News Search Claude

- **URL**: `/api/v1/NewsClaude`
- **Method**: POST
- **Description**: Performs a news search using the Claude model

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/NewsClaude"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Recent breakthroughs in space exploration"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/NewsClaude" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Recent breakthroughs in space exploration\"}}"
```

#### News Search Evidence

- **URL**: `/api/v1/NewsEvidence`
- **Method**: POST
- **Description**: Searches for evidence in news-related contexts

**Python Example**:

```python
import requests

url = "http://172.190.86.16:8000/api/v1/NewsEvidence"
headers = {"Content-Type": "application/json"}
data = {"input": {"query": "Factual evidence in recent political developments"}}

with requests.post(url, json=data, headers=headers, stream=True) as response:
    for chunk in response.iter_content(chunk_size=None, decode_unicode=True):
        print(chunk, end='', flush=True)
```

**cURL Example**:

```bash
curl -X POST "http://172.190.86.16:8000/api/v1/NewsEvidence" -H "Content-Type: application/json" -d "{\"input\": {\"query\": \"Factual evidence in recent political developments\"}}"
```

## Error Handling

The API may return standard HTTP status codes to indicate the success or failure of a request. Common status codes include:

- 200 OK: The request was successful
- 400 Bad Request: The request was invalid or cannot be served
- 500 Internal Server Error: The server encountered an unexpected condition

In case of an error, the response body may contain additional information about the error. It's recommended to implement proper error handling in your code to manage these scenarios.

## Rate Limiting

Currently, there is no specified rate limiting for the API. However, users should be mindful of their usage and avoid overwhelming the server with too many requests in a short period.

## Best Practices

1. Process streaming responses in real-time for best performance.
2. Implement appropriate error handling in your code.
3. Keep your queries concise and specific for more accurate results.
4. Respect the server resources and avoid sending too many requests in rapid succession.
5. Regularly check for updates to the API and its documentation.
6. Maintain the confidentiality of the API endpoints and your usage.

## Troubleshooting

If you encounter issues while using the API:

1. Double-check the endpoint URL and ensure it's correct.
2. Verify that your request payload is properly formatted JSON.
3. Check your network connection and the API server status.
4. If you're not receiving a response, ensure you're properly handling the streaming nature of the response.
5. For persistent issues, review your code for any potential errors in making the request or processing the response.

## Changelog

- Pre-Beta Version 1.0.4: Current version

## Contact Information

For additional support, questions, or to report issues with the API, please contact the API provider.

Aditya Vardhan: aditya.vardhan2009@gmail.com