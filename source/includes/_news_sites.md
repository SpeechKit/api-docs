# News sites

## Get all your news sites

```shell
curl "https://app.speechkit.io/api/v1/news_sites"
  -H "Authorization: Token=token {READ_API_KEY}"
```

> Example response:

```json
[
  {
    "id": 28,
    "title": "Bloomberg",
    "external_id": "bloomberg"
  },
  {
    "id": 29,
    "title": "The Guardian",
    "external_id": "the-guardian"
  },
  {
    "id": 30,
    "title": "Der Tagesspiegel",
    "external_id": "der-tagesspiegel"
  }
]
```

This endpoint retrieves all news sites that belong to your publisher.

### HTTP Request

`GET https://app.speechkit.io/api/v1/news_sites`


## Create a new news site

```shell
curl -X POST -d '{"title": "My site"}' "https://app.speechkit.io/api/v1/news_sites"
  -H "Authorization: Token=token {WRITE_API_KEY}"
```

> Example response:

```json
{
  "id": 1,
  "title": "My Site",
  "external_id": "my-site"
}
```

This endpoint allows you to add sites to your publisher.

### HTTP Request

`POST https://app.speechkit.io/api/v1/news_sites`

### Parameters

Parameter | Default | Description
--------- | ------- | -----------
title | "" | The name of your site. This is for your own reference

