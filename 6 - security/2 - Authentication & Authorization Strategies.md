# Authentication & Authorization Strategies

Authentication is for verifies identity. ( who are you? )

Authorization is used to determine permissions. What can you do?

## Authentication.

Common methods: username/password, multi-factor authentication, OAuth/social login, biometrics, certificate-based, single sign-on (SSO).

### Stateful: session-based, server stores session, Fast evaluation.
### Stateless.: Token-based, client stores token, more complex invalidation.

In the context of distributed systems, the stateless approach is better. Because we don't want to tie it to any specific server.

However, stateful is a lot easier to implement. Hence, you can invalidate a lot faster.

## Authorization

Auth layers: API gateway level, service level, database level, objects/data level.

<hr />

### Session based.

Authenticate user. Store authentication in memory (session). Validate session on each request.


### Common token types

- JWT (JSON Web Tokens)
- Session Tokens
- API Keys
- OAuth Tokens

### Client storage.

Cookies, Local storage, Session storage / Memory

## Summary

Stateless architecture makes scaling easier.