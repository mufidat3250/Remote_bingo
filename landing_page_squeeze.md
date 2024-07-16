# Squeeze Page Api Endpoint [POST] /api/v1/pages/squeeze

## Description

*If a user wants a copy of the boilerplate, the person would input a valid email address into the form and press the button to submit. The email will get validated and sanitized. If the email fails the validation an error message would be returned. If successful, the email will be added to the squeeze_table and a successful response will be sent to the client. This endpoint gets the user information for database storage.*

## Expected Outcome
- The user input data should be successfully sent to the backend, or the user will receive an error message if unsuccessful

## Acceptance Criteria:
- User's email format correct, if not, the user receives an error message

## Requirements
- A valid email address

**Status code**
- **201**: Email was successfully stored.
- **400**: Invalid email address.
- **401**: Email already exist.
- **500**: A server error occurred.

**Requests:**

*headers:*
- content-type: application/json

```json
{
    "email": "string"
}
```
**Responses:**

*Successful response*
```json
{
    "message": "string",
    "success": true,
}
```

*Error response*
```json
{
    "message": "string",
    "success": false,
}
```

## Database design
**schema**

**Table name: squeeze_table**

*id:*
- constraints: string(uuid), unique, primary-key, not null

*email:*
- constraints: string, unique, not null, length(150)

*createdAt:*
- constraints: string, date timestamp
