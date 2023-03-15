# Version

### `GET /api/v1/version`

Returns the version of the API and the front-ends.

=== "200 OK"
    ```json
    {
      "status": 1,
      "message": "A random message for every request!",
      "messageCode": "RANDOM_MESSAGE",
      "data": {
        "api": {
          "versionNumber": 1,
          "versionName": "v1-0.1.0-beta",
          "changeLog": "Initial release"
        },
        "android": {
          "versionNumber": 1,
          "versionName": "1.0.0-alpha",
          "changeLog": "- Example",
          "updateUri": "https://zz-cdn.theclashfruit.me/dl/android/3.0.0-alpha.apk"
        },
        "web": {
          "http": {
            "versionName": 1,
            "versionNumber": "1.0.0-alpha",
            "changeLog": "- Example",
            "updateUri": "https://zz.theclashfruit.me/"
          },
          "windows": {
            "versionName": 1,
            "versionNumber": "1.0.0-alpha",
            "changeLog": "- Example",
            "updateUri": "https://zz-cdn.theclashfruit.me/dl/web/win32/3.0.0-alpha.exe"
          },
          "linux": {
            "versionName": 1,
            "versionNumber": "1.0.0-alpha",
            "changeLog": "- Example",
            "updateUri": "https://zz-cdn.theclashfruit.me/dl/web/linux/3.0.0-alpha.AppImage"
          },
          "darwin": {
            "versionName": 1,
            "versionNumber": "1.0.0-alpha",
            "changeLog": "- Example",
            "updateUri": "https://zz-cdn.theclashfruit.me/dl/web/darwin/3.0.0-alpha.dmg"
          }
        }
      }
    }
    ```

=== "500 Internal Server Error"
    ```json
    {
      "status": 0,
      "message": "An internal server error occurred!",
      "messageCode": "INTERNAL_SERVER_ERROR",
      "data": null
    }
    ```