# Security Risk Escalation API Specification

This API specification outlines the methods and endpoints for Fidelity's Security Risk Escalation feature.

## Base URL

Requests can be sent to the following base URL:
`https://api.fidelity.com`

## Supported API Methods

### Create Risk 

Creates a new risk assessment.

* Method: POST
* Endpoint: `/risk-assessments`

#### Request Body

``` json
{
  "title": "string",
  "description": "string",
  "severity": "string",
  "assigned_to": "[string]"
}
```

#### Response Body

``` json
{
  "status": "string",
  "message": "string"
}
```

### Get Risk Assessment

Retrieves a specific risk assessment by its `id`.

* Method: GET
* Endpoint: `/risk-assessments/{id}`

#### Response Body

``` json
{
  "id": "string",
  "title": "string",
  "description": "string",
  "severity": "string",
  "assigned_to": "string"
}
```

### Update Risk Assessment

Updates an existing risk assessment. All request fields are optional, so that users can update only the necessary fields.

* Method: PUT
* Endpoint: `/risk-assessments/{id}`

#### Request Body

``` json 
{
  "title": "[string]",
  "description": "[string]",
  "severity": "[string]",
  "assigned_to": "[string]",
  "issue_state": "[string]"
}
```

#### Response Body

``` json
{
  "status": "string",
  "message": "string"
}
```

### Delete Risk Assessment

Deletes an existing risk assessment.

* Method: DELETE
* Endpoint: `risk-assessments/{id}`

#### Response Body

``` json
{
  "status": "string",
  "message": "string"
}
```

### Delete Escalation

Delete a risk assessment.

* Method: DELETE
* Endpoint: `/risk-assessments/id`

Body Response:

``` json
{
  "status": "string",
  "message": "string"
}
```

## Error Handling

In case of errors, the API will return the following JSON response:

``` json

{
  "status": "",
  "message": ""
}
```

The possible HTTP status codes and their associated messages include:

* 200 - OK: Successful request.
* 400 - Bad Request: Invalid request parameters or missing required fields.
* 401 - Unauthorized: Missing or invalid API key.
* 404 - Not Found: Risk assessment not found.
* 500 - Internal Server Error: An error occurred while processing the request.
