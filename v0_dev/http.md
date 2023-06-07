# HTTP Server Specification

Default port: `39979`

Server must support `HTTP/2`


# Endpoints

## `/device_info`
- Method: `GET`
- Request: empty
- Response:
  - Content-Type: `application/json`
  - Body: [Device Info](device_info.md)

## `/ask`
- Method: `POST`
- Request:
  - Content-Type: `application/json`
  - Body:
    ```jsonc
    {
        "sender": {}, // See device_info.md
        "files": [
            {
                "name": "file.txt", // not path, only base name
                "size": 2382396 // int64 file size
            }
        ]
    }
    ```
- Response:
  - Content-Type: `application/json`
  - Body:
      ```jsonc
      {
          "accepted": true // or false
      }
      ```

## `/send`

This endpoint is still unstable and may change in the future

- Method: `POST`
- Request: 
  - Body: [TFA Archive](v0_dev/tfa.md) 
  - Chunked transferring
- Response: empty
