# Authentication

The REST API uses an authentication scheme based on this OAuth 2 specification. All requests to resources
(exclusing the *schema* pages) must be accompanied by a correct <font color=red>Authorization</font> header as per this specification. The header looks like this:

 	Authorization: api_key=your API key,ts=YYYY-MM-DD HH24:MI:SSS +0000,nonce=random-string,x_security_sign=base64-encoded-hash

Note: Some OAuth 2 specifications show this header split across multiple lines. We do not support this. Ensure the header is on one line.
Authorization header fields
The value of the header is made up of the following components.

	*   api_key

 Your API key, issued to you by REST API. You can create an API key in your developer portal account.

	*   ts

The Unix timestamp of the time you made the request. We allow a slight buffer on this in case of any time sync issues.

	*   nonce

A randomly generated string of your choice. Ensure it is unique to each request, and no more than 32 characters long.
(To prevent replay attacks, a single nonce can only be used once.)

	*	x_security_sign

This is the base 64 encoded hash of the request.
Calculating the sign hash
The hash is a MD5-hash digest of a concatenation of a series of strings related to the request. The string is:
###Base64(MD5(apiKey+secret key+ timestamp+nonce))

HTTP request method

HTTP request URI

HTTP host

HTTP port

Once the hash is calculated, base 64 encode it and include it in the HTTP header. For this example, the hashed string is:
GfQ15pg5cEOieC5QaGyCHRxnPv4fGHerOh6w7YRD0Q