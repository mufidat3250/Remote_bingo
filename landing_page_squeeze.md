# Squeeze Page Api Endpoint 
**[POST] /api/v1/pages/squeeze**

## Description

*If a user wants a copy of the boilerplate, the person would input a valid email address into the form and press the button to submit. The email will get validated and sanitized. If the email fails the validation an error message would be returned. If successful, the email will be added to the squeeze_table and a successful response will be sent to the client. This endpoint gets the user information for database storage.*

## Expected Outcome
- The user input data should be successfully sent to the backend, or the user will receive an error message if unsuccessful

## Acceptance Criteria:
- User's email format correct, if not, the user receives an error message

## Requirements
- [ ] A valid email address
- [ ] An API endpoint with data validation and sanitization
- [ ] Set up database integration and secure storage
- [ ] Add rate limiting and CSRF protection measures
- [ ] Integrate email service for confirmation messages
- [ ] Conduct security testing and performance optimization


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
    "statusCode": Int
}
```

*Error response*
```json
{
    "message": "string",
    "success": false,
     "statusCode": Int
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

## Testing

1. Unit Tests

The systems should have unit tests covering:
- [ ] rate limiting and CSRF protection measures
- [ ] the setting up database integration and secured storage
- [ ] email integration service for confirmation messages
- [ ] Conduct security testing and performance optimization 
- [ ] Implement API endpoint with data validation and sanitization
