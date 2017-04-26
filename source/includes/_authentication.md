# Authentication

> To authorize, use this code:

```shell

curl "https://app.speechkit.io/api/v1/{endpoint}"
  -H "Authorization: Token=token {WRITE_API_KEY}"
```

The speechkit API uses token authentication. You should have received 2 keys, one write key and one read only key.
You can request a key from signing up on our website: [https://speechkit.io](https://speechkit.io)

* `WRITE_API_KEY`: Should be used from your back end to generate audio
* `READ_API_KEY`: Should be used in your clients for reading information about previsouly generated audio.

<aside class="warning">
Your <code>WRITE_API_KEY</code> should only be used from your backend or any other secure location, where no one else can view it.
</aside>

