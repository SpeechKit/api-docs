# Articles

## Get All Articles

```shell
curl "https://app.speechkit.io/api/v1/news_sites/{news_site_id}/articles"
  -H "Authorization: Token=token {READ_API_KEY}"
```

> Example response:

```json
[
  {
    "id": "1",
    "url": "https://www.bloomberg.com/news/articles/2016-09-09/google-s-ai-brainiacs-achieve-speech-generation-breakthrough",
    "title": "Google’s DeepMind Achieves Speech-Generation Breakthrough",
    "author": "Jeremy Khan",
    "summary": "",
    "image": "",
    "published_at": "2016-09-09T13:03:00.000Z",
    "body": "Google’s DeepMind Achieves Speech-Generation Breakthrough.....",
    "state": "processed",
    "media": [
      {
        "id": 25726,
        "role": "body",
        "content_type": "application/x-mpegURL",
        "url": "https://d22tbkdovk5ea2.cloudfront.net/audio/news_sites/28/articles/12860/roles/body/voices/37/ab6faf941b7f604a77a60c5ebcacda82.m3u8",
        "created_at": "2017-04-25T13:05:15.536Z",
        "state": "processed"
      },
      {
        "id": 25725,
        "role": "body",
        "content_type": "audio/mpeg",
        "url": "https://d22tbkdovk5ea2.cloudfront.net/audio/news_sites/28/articles/12860/roles/body/voices/37/c9d36a0c25e84d98c5a40f4a6ca510ca.mp3",
        "created_at": "2017-04-25T13:05:06.450Z",
        "state": "processed"
      }
    ]
  }
]
```

This endpoint retrieves all articles for a news site.

### HTTP Request

`GET https://app.speechkit.io/api/v1/news_sites/{news_site_id}/articles?page={page}`

### Parameters

Parameter | Default | Description
--------- | ------- | -----------
news_site_id | none | The id of your site you want to fetch all articles for. This can also be your news_sites external id
page | 1 | Since this is a paginated response you can set the page to get more articles.



## Get A Specific Article

```shell
curl "https://app.speechkit.io/api/v1/news_sites/{news_site_id}/articles/{article_id}"
  -H "Authorization: Token=token {READ_API_KEY}"
```

> Example response:

```json
{
  "id": "1",
  "url": "https://www.bloomberg.com/news/articles/2016-09-09/google-s-ai-brainiacs-achieve-speech-generation-breakthrough",
  "title": "Google’s DeepMind Achieves Speech-Generation Breakthrough",
  "author": "Jeremy Khan",
  "summary": "",
  "image": "",
  "published_at": "2016-09-09T13:03:00.000Z",
  "body": "Google’s DeepMind Achieves Speech-Generation Breakthrough.....",
  "state": "processed",
  "media": [
    {
      "id": 25726,
      "role": "body",
      "content_type": "application/x-mpegURL",
      "url": "https://d22tbkdovk5ea2.cloudfront.net/audio/news_sites/28/articles/12860/roles/body/voices/37/ab6faf941b7f604a77a60c5ebcacda82.m3u8",
      "created_at": "2017-04-25T13:05:15.536Z",
      "state": "processed"
    },
    {
      "id": 25725,
      "role": "body",
      "content_type": "audio/mpeg",
      "url": "https://d22tbkdovk5ea2.cloudfront.net/audio/news_sites/28/articles/12860/roles/body/voices/37/c9d36a0c25e84d98c5a40f4a6ca510ca.mp3",
      "created_at": "2017-04-25T13:05:06.450Z",
      "state": "processed"
    }
  ]
}
```

This endpoint retrieves a specified article.

### HTTP Request

`GET https://app.speechkit.io/api/v1/news_sites/{news_site_id}/articles/{article_id}`

### Parameters

Parameter | Default | Description
--------- | ------- | -----------
news_site_id | none | The id of your site you want to fetch all articles for. This can also be your news_sites external id
article_id | none | The id of the article you want to request.


