# JSON Web Tokens (JWT)
is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object.

- JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.
- Signed tokens can verify the integrity of the claims contained within it, while encrypted tokens hide those claims from other parties
### When should you use JSON Web Tokens?
- Authorization
- Information Exchange
### What is the JSON Web Token structure?
- Header
- Payload
  - There are three types of claims: registered, public, and private claims.
  - The payload is then Base64Url encoded to form the second part of the JSON Web Token.
- Signature 

### How do JSON Web Tokens work?

-  how a JWT is obtained and used to access APIs or resources:

  - The application or client requests authorization to the authorization server. This is performed through one of the different authorization flows. 
  - When the authorization is granted, the authorization server returns an access token to the application.
  - The application uses the access token to access a protected resource (like an API).

### Why should we use JSON Web Tokens?
1. As JSON is less verbose than XML
2. Security-wise, SWT can only be symmetrically signed by a shared secret using the HMAC algorithm. 
3. JSON parsers are common in most programming languages because they map directly to objects
4. Regarding usage, JWT is used at Internet scale. 


# DRF JWT Authentication
The JWT is just an authorization token that should be included in all requests:
- The JWT is acquired by exchanging an username + password for an access token and an refresh token.
- The access token is usually short-lived
- The refresh token lives a little bit longer

### Usage
I will be using HTTPie to consume the API endpoints via the terminal. But you can also use cURL (readily available in many OS) to try things out locally.

- The endpoint is /api/token/ and it only accepts POST requests.
- In order to access the protected views on the backend , you should include the access token in the header of all requests,You can use this access token for the next five minutes.
- **Refresh Token** To get a new access token, you should use the refresh token endpoint /api/token/refresh/ posting the refresh token
- The return is a new access token that you should use in the subsequent requests.
- The refresh token is valid for the next 24 hours

### What’s The Point of The Refresh Token?
- it is necessary to make sure the user still have the correct permissions.
- There is also a security aspect, in a sense that the refresh token only travel in the POST data. And the access token is sent via HTTP header, which may be logged along the way. So this also give a short window, should your access token be compromised.


# Django Runserver Is Not Your Production Server
- So the server started with runserver is not guaranteed to be performant (it’s very slow), and it hasn’t been built with security concerns in mind. Not a good fit for production use.

### production setup
- usually consists of multiple components, each designed and built to be really good at one specific thing. They are fast, reliable and very focused.

- When a request arrives at your server, it should be passed to a dedicated web server. **Nginx** is an example for a good web server.
- If the request is not for a static file, but should be processed by your application, the webserver is configured to pass this request to the next component.
