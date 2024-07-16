## Acceptance Criteria

### Get All Topics [GET] `/api/topics

1. Endpoint Flow

- This endpoint runs by default on page load, and queries the database for all the topics in the `topics` table.

Request

```
[GET] /api/topics
```

Successful Response `200`

```
{
    "success": true,
    "message": String,
    "topics": [
        {
            "title": String,
            "content": String,
            "article_id": Int,
        }
        ...
    ]
}
```

Error Response `500`

```
{
    "success": false,
    "message": String,
    "statusCode": 500
}
```

<br />

### Search for topics

1. Endpoint `/api/topic` will accept query parameters that would be queried across the `topic's title` column.
   <br/>
2. If debouncing is not setup on the frontend, rate limiting error should be thrown.
   <br />

Request

```
[GET] /api/topics?title={title}

query param - title
```

Successful Response: `200`

```
{
    "success": true,
    "message": String,
    "topics": [
        {
            "title": String,
            "content": String,
            "id": Int,
        },
        ...
    ]
}
```

Error Response: `404`
No article matching the title search param

```
{
    "success": false,
    "message": String,
    "statusCode": 404
}
```

Error Response: `429`
Too many requests, implement Debouncing

```
{
    "success": false,
    "message": String,
    "statusCode": 429
}
```

Error Response: `500`
Internal Server Error

```
{
    "success": false,
    "message": String,
    "statusCode": 500
}
```

### Newsletter Signup

## [TO REMOVE IF IMPLEMENTED ON OTHER PAGES]

1. The endpoint stores emails of users that wants to sign up for newsletter

2. Avoid storing multiple email entries.

Request

```
POST /api/newsletter
{
    "email": String
}
```

Successful Response: `201`

```
{
    "success": true,
    "message": String
}
```

Error Response: `409`

- Throw error when email already exists

```
{
    "success": false,
    "message": String,
    "statusCode": 409
}
```

Error Response: `400`

- Throw error on bad request (email validation)

```
{
    "success": false,
    "message": String,
    "statusCode": 400
}
```

Error Response: `500`
Internal Server Error

```
{
    "success": false,
    "message": String,
    "statusCode": 500
}
```

### Testing

1. Unit Tests

- The systems should have unit tests covering rate limit check.

- The return data for the `/api/topics` matches the doc.
