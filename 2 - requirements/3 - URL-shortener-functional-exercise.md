# URL Shortener Functional Requirements

You're desigining a service that converts LONG URLs into SHORTER, more manageable links.

What are the questions you migh ask?
What are examples of NON-functional requirements?

## QUESTIONS

- Can users customize the shortened URL?
- How do we protect the users from malicious links?
- is it a LIMIT on HOW MANY urls created per user?
- can URL expired
- Would we support paid tier, free tier? (are there different levels of user?)
- Is there a maximum length for the URL?
- what is the expected output fo a shortened link?
- Are URL's limited to HTTP/HTTPs
- How can the short link be represented? (QR code supported?)
- Can the links be edited?
- Do we need analytics on the links? (admin panels to view statistic)
- Do users need to create an account to make shortlinks?
- Can multiple shortlinks link to the same long url?

## FUNCTIONAL

- users should be able to convert long URL's into shortened versions
- users need create accounts to edit their urls
- users are limited to 50 short links
- there are free users and paid users
- paid users require an account with email and password.
- paid users have NO expiration of links, free users expire after 6 months

### Important considerations include:

What constitutes a valid URL? Should URLs be restricted to HTTPS or can other protocols be supported?
How should query parameters be handled - should URLs with the same parameters in different orders be treated as equivalent? What is the maximum length for a short URL to still be considered useful?

### Important security considerations include:

How to protect users from malicious redirects (such as showing a preview or requiring confirmation before navigation), whether to display the full URL before redirecting, and how to validate and sanitize input URLs to prevent abuse.

### 'deterministic' shortening process and what are its trade-offs

A deterministic shortening process means that the same input URL always generates the same short URL.

This approach minimizes database usage by reusing existing short URLs for duplicate long URLs.

However, if users need accounts with the ability to edit or manage links individually, a non-deterministic approach may be better to give each user unique links even for the same destination URL.

### scale-related questions should be asked when designing a URL shortening service, and how do they impact the design?

Important scale questions include:

How many URLs do we anticipate supporting in total (per day, month, or year)?

What is the expected volume of requests?

These numbers impact decisions about short code generation strategies, database design, caching strategies, and whether link reuse (deterministic hashing) is beneficial or if unique links per user are needed.