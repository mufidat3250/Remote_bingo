# NewsLetter Page Api Endpoint [POST] /api/v1/pages/newsletter

## Description

- A potential user sends requests with information(email).
- The user email is validated and sanitized.
- If the user email fails the validation, an error mesage is sent to them.
- On successful validation, the email is added to the subscribers_table and a success response is sent to the user.

## Expected Outcome
- The user input data should be successfully sent to the backend, or the user will receive an error message if unsuccessful

## Acceptance Criteria:
- User's email format correct, if not, user receives an error message

## Requirements
- A valid email address

**Status code**
- **201**: You have successfully subscribed to our newsletter.
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

**Table name: subscribers_table**

*id:*
- constraints: string(uuid), unique, primary-key, not null

*email:*
- constraints: string, unique, not null, length(150)

*createdAt:*
- constraints: string, date timestamp
