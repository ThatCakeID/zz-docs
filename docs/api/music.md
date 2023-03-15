# Music

!!! warning
    The `/api/v1/music/*` endpoints are still under heavy development and breaking changes are to be expected.

## Music Status Codes

|    Status    |  Code  |
|:------------:|:------:|
| `Processing` |   0    |
|  `Withheld`  |   1    |
|  `Private`   |   2    |
|   `Public`   |   3    |

## Uploading

!!! note
    Uploading is a bit tedious due to the fact the metadata extraction is done on the backend.

    A basic view of the uploading process:

    1. Upload the music: `PUT /api/v1/music/upload` (multipart/form-data)
      ```
      file=[file.ogg]
      ```
    2. Review the metadata.
    3. Upload the changed metadata: `PATCH /api/v1/music/:uuid` (multipart/form-data)
      ```
      thumbnail=[file.jpg]
      data={ ..., "status": 3 }
      ```

### 1. `PUT /api/v1/music/upload`

Upload a music.

Headers:
```http
Authorization: Bearer a.jwt.token
Content-Type: multipart/form-data
```

Body:
```http
file=[file.ogg]
```

=== "200 OK"
    ```json
    {
      "status": 1,
      "message": "Successfully uploaded music.",
      "messageCode": "MUSIC_UPLOADED",
      "data": {
        "uuid": "f34fa77d-02b3-46fa-864f-218a8bb8f399",
        "author": "a49171b1-cb49-41bd-aa3d-2e53aca2e1d3",
        "url": "https://zz-cdn.theclashfruit.me/f34fa77d-02b3-46fa-864f-218a8bb8f399/Martin_Garrix___Bebe_Rexha_-_In_The_Name_Of_Love__Official_Video_.mp3",
        "thumbnail": "https://zz-cdn.theclashfruit.me/f34fa77d-02b3-46fa-864f-218a8bb8f399/thumbnail.jpg",
        "metaData": {
          "bitRate": 124105.32475131656,
          "sampleRate": 48000,
          "replayGain": 0,
          "duration": 205.08,
          "title": 	"Martin Garrix & Bebe Rexha - In The Name Of Love (Official Video)",
          "authors": [
            "Martin Garrix"
          ],
          "genre": "Unkonwn",
          "year": 2016,
        },
        "stats": {
          "views": 503,
          "likes": [ "a49171b1-cb49-41bd-aa3d-2e53aca2e1d3" ],
          "comments": [ { ... } ],
        },
        "uploadedAt": 1678649671025,
        "updatedAt": 1678649671056
      }
    }
    ```

### 2. `PATCH /api/v1/music/:uuid`

Update the metadata of a music.

Headers:
```http
Authorization: Bearer a.jwt.token
Content-Type: multipart/form-data
```

Body:
```http
thumbnail=[file.jpg]
data={
  "status": 3,
  "metaData": {
    "title": "...",
    "authors": [ "..." ],
    "genre": "...",
    "year": "2023",
  }
}
```

=== "200 OK"
    ```json
    {
      "status": 1,
      "message": "Successfully uploaded music.",
      "messageCode": "MUSIC_UPLOADED",
      "data": {
        "uuid": "f34fa77d-02b3-46fa-864f-218a8bb8f399",
        "author": "a49171b1-cb49-41bd-aa3d-2e53aca2e1d3",
        "url": "https://zz-cdn.theclashfruit.me/f34fa77d-02b3-46fa-864f-218a8bb8f399/Martin_Garrix___Bebe_Rexha_-_In_The_Name_Of_Love__Official_Video_.mp3",
        "thumbnail": "https://zz-cdn.theclashfruit.me/f34fa77d-02b3-46fa-864f-218a8bb8f399/thumbnail.jpg",
        "metaData": {
          "bitRate": 124105.32475131656,
          "sampleRate": 48000,
          "replayGain": 0,
          "duration": 205.08,
          "title": 	"Martin Garrix & Bebe Rexha - In The Name Of Love (Official Video)",
          "authors": [
            "Martin Garrix"
          ],
          "genre": "Unkonwn",
          "year": 2016,
        },
        "stats": {
          "views": 503,
          "likes": [ "a49171b1-cb49-41bd-aa3d-2e53aca2e1d3" ],
          "comments": [ { ... } ],
        },
        "uploadedAt": 1678649671025,
        "updatedAt": 1678649671056
      }
    }
    ```