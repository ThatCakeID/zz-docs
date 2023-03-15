# User

!!! warning
    The `/api/v1/user/*` endpoints are still under heavy development and breaking changes are to be expected.

### `GET /api/v1/user/@me`

Get the currently logged-in user.

Headers:
```http
Authorization: Bearer a.jwt.token
```

=== "200 OK"
    ```json
    {
      "status": 1,
      "message": "Successfully fetched user!",
      "messageCode": "SUCCESS_FETCH_USER",
      "data": {
        "uuid": "182d17a4-c31a-11ed-afa1-0242ac120002",
        "username": "example",
        "email": "example@example.com",
        "bio": "bio",
        "avatar": "https://zz-cdn.theclashfruit.me/userImage.png",
        "createdAt": 1678875181
        "updatedAt": 1678875181
      }
    }
    ```

=== "404 Not Found"
    ```json
    {
      "status": 0,
      "message": "User not found!",
      "messageCode": "NOT_FOUND",
      "data": null
    }
    ```