# Errors

The errors you can expect coming out from Speechkit.io API


Error Code | Meaning
---------- | -------
401 | Unauthorized -- If you're API key does not have access to do what you're trying to do.
404 | Not Found -- The speicifed resource you were trying to access does not exist
422 | Unprocessable entity -- Whatever you tried to create you didn't pass validation. Reasons are in response.
500 | Unknown -- Everything else comes back as a 500.