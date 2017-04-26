# Voices

## Get All Voices

```shell
curl "https://app.speechkit.io/api/v1/voices"
```

> Example response:

```json
[
  {
    "id": 1,
    "language": "en_AU",
    "name": "Nicole"
  },
  {
    "id": 2,
    "language": "en_AU",
    "name": "Russel"
  }
]
```

This endpoint retrieves all voices available from speechkit

### HTTP Request

`GET https://app.speechkit.io/api/v1/voices`
