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

# Django Runserver Is Not Your Production Server