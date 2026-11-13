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

###  What is a sticky session and why does it occur when authentication is handled at the web server level?

A sticky session means that every request from a client must go to the same server every time. 
This occurs when authentication state is maintained on individual web servers rather than being shared between servers. 

The routing algorithm ensures requests are directed to the same server based on session ID or another parameter. 

This becomes problematic when scaling up or down, which is why authentication is better placed at the edge.

### the trade-offs between using short-lived JWT tokens versus session-based authentication?

Short-lived JWT tokens limit the time window a compromised token can be used (potentially 30 seconds to a couple minutes), but require more resources and frequent client reauthentication with refresh tokens. 

Session-based authentication is faster, can be deauthenticated quickly, and is more logical (sessions end when browser tabs close), but is more stateful and tied to specific servers.

- Stateless authentication allows systems to scale up and down easily without being tied to particular servers. 
If a server goes down, requests can automatically switch to another server. 

This is especially important in microservice architectures where services need to authenticate with each other.

However, stateful authentication is easier to implement and allows for faster invalidation of credentials.

###  the two main security approaches for microservice architectures, and what are their trade-offs?

The first approach is building a strong perimeter defense where once inside, users can move freely. 

This is easier to program but vulnerable to social engineering attacks, and breaches can go undetected. 

The second approach requires explicit permissions for every action with no implicit trust. This is more secure but heavier and more difficult to work with, requiring validation for every microservice request.