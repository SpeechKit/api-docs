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





## Create an article (with audio)

```shell
curl -X POST -d '{
	"external_id": 1,
	"title": "The title of my article",
	"published_at": "2017-02-03",
	"author": "John Doe",
	"summary": "My summary of the article",
	"body": "This is the body of the article",
	"media_attributes": [{
		"role": "summary",
		"voice_id": 1
	}, {
		"role": "body",
		"voice_id": 1
	}]
}' "https://app.speechkit.io/api/v1/news_sites/{news_site_id}/articles"
  -H "Authorization: Token=token {WRITE_API_KEY}"
```

> Example response:

```json
{
  "id": "1141123123",
  "url": null,
  "title": "The title of my article",
  "author": "John Doe",
  "summary": "My summary of the article",
  "image": null,
  "published_at": "2017-02-03T00:00:00.000Z",
  "body": "This is the body of the article",
  "state": "unprocessed",
  "media": [
    {
      "id": 208,
      "role": "summary",
      "content_type": "",
      "url": null,
      "created_at": "2017-04-26T11:48:29.069Z",
      "state": "unprocessed",
      "voice": {
        "id": 1,
        "language": "en_GB",
        "name": "en-GB_KateVoice"
      }
    },
    {
      "id": 209,
      "role": "body",
      "content_type": "",
      "url": null,
      "created_at": "2017-04-26T11:48:29.071Z",
      "state": "unprocessed",
      "voice": {
        "id": 1,
        "language": "en_GB",
        "name": "en-GB_KateVoice"
      }
    }
  ]
}
```

Create an article for your site. Every time you create an article we build the audio for you.

<aside class="notice">
  Make sure the <code>state</code> of the article is "processed" to ensure that it has been generated, transcoded, etc.
</aside>



### HTTP Request

`POST https://app.speechkit.io/api/v1/news_sites/{news_site_id}/articles`

### Parameters

Parameter | Default | Description
--------- | ------- | -----------
external_id | none | The id you want to identify this article as. Needs to be unique
title | none | The title of the article
published_at | none | When this article was originally published
author | none | The name of the author for this article
summary | none | The summary of the article
body | none | The complete body of the article
media_attributes | none | This is an array containing all media files you want produced.
media_attributes[:role] | none | The role specifies what part of the article you want synthesized
media_attributes[:voice_id] | none | The voice id you want to use for this synthesis.


