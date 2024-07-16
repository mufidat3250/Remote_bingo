# Squeeze Page Api Endpoint [POST] /api/v1/pages/squeeze

## Description

- A potential user sends requests with information(email).
- The user email is validated and sanitized and is securely stored in the database.
- If the user email fails the validation, an error message is sent to them.
- On successful validation, a confirmation email is sent to the user's email securely.

## Expected Outcome
- The user input data should be successfully sent to the backend, or the user will receive an error message if unsuccessful

## Acceptance Criteria:
- User's email format correct, if not, user receives an error message

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
