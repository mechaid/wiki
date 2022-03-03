---
title: JSON Web Tokens
layout: wiki-page
tags: [jwt, kriptografi, cryptography, rfc]
---

## Definisi
- **Asana**: 
  - Open standard
  - Used to share security information
  - Between two parties — a client and a server
  - Each JWT contains encoded JSON objects, including a set of claims
  - JWTs are [signed](https://stackoverflow.com/a/454069) using a [cryptographic algorithm](https://www.sciencedirect.com/topics/computer-science/cryptographic-algorithm) to ensure that the claims cannot be altered after the token is issued.
- [**JWT.io**](https://jwt.io/introduction):
  - Open standard ([RFC 7519](https://datatracker.ietf.org/doc/html/rfc7519))
  - Defines a compact and self-contained way
  - For securely transmitting information between parties
  - As a JSON object
  - This information can be verified and trusted because it is digitally signed
  - Can be signed using a [secret](https://www.hypr.com/secret-key/) (with the HMAC algorithm)
  - Or a [public/private key pair](https://www.sciencedirect.com/topics/computer-science/private-key-pair) using RSA or ECDSA.
- [**IBM**](https://www.ibm.com/docs/en/sva/10.0.2?topic=types-json-web-token-jwt):
  - Set of JSON claims that are signed, encrypted, or both
  - Are encoded into a web safe form
  - This set of claims might or might not include some well-known claims that are defined by the RFC. 
- [**Auth0**](https://auth0.com/docs/security/tokens/json-web-tokens):
  - Pronounced "jot"
  - Open standard (RFC 7519)
  - Defines a compact and self-contained way
  - For securely transmitting information between parties
  - As a JSON object
  - Is a standard, meaning that all JWTs are tokens, but not all tokens are JWTs
- [**KrakenD**](https://www.krakend.io/docs/authorization/jwt-overview/):
  - Industry standard
  - Represent claims securely between two parties
  - An encoded JSON object
  - Contains key-value pairs of attributes that are signed by a trusted authority.

## Artikel Terkait
- [IETF - JSON Web Key (JWK)](https://tools.ietf.org/id/draft-ietf-jose-json-web-key-00.html)
