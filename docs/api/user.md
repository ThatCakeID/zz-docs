# User

### `GET /api/v1/user/@me`

Get the current user.

Headers:
```
Authorization: Bearer a.jwt.token
```

<details>
  <summary>200 OK</summary>

  <pre>
  {
    "status": 1,
    "message": "Successfully fetched user!",
    "messageCode": "SUCCESS_FETCH_USER",
    "data": {
      "uuid": "uuid",
      "username": "example",
      "email": "example@example.com",
      "bio": "bio",
      "avatar": "avatarUrl",
      "createdAt": 10000000
    }
  }
  </pre>
</details>

### `PATCH /api/v1/user/@me`

Update the current user.

Headers:
```
Authorization: Bearer a.jwt.token
Content-Type: application/json
```

Body:
```json
{
  "username": "example",
  "email": "example@example.com",
  "bio": "bio"
}
```

<details>
  <summary>200 OK</summary>

  <pre>
  {
    "status": 1,
    "message": "Successfully fetched user!",
    "messageCode": "SUCCESS_FETCH_USER",
    "data": {
      "uuid": "uuid",
      "username": "example",
      "email": "example@example.com",
      "bio": "bio",
      "avatar": "avatarUrl",
      "createdAt": 10000000
    }
  }
  </pre>
</details>

### `POST /api/v1/user/@me/avatar`

Update the current user's avatar.

Headers:

```
Authorization: Bearer a.jwt.token
Content-Type: multipart/form-data
```

Body:

```
file=avatarFile
```

<details>
  <summary>200 OK</summary>

  <pre>
  {
    "status": 1,
    "message": "Successfully fetched user!",
    "messageCode": "SUCCESS_FETCH_USER",
    "data": {
      "avatar": "avatarUrl"
    }
  }
  </pre>
</details>
