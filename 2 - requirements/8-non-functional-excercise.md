# Non-Functional Requirements for banking application

## Questions

- How many MAU's? (Monthly Active Users)
- How many transaction per user?
- How frequent are the transactions?
- How LONG do we store transaction data?
- What is the minimum latency for a transaction
- what is our availability target?
- How consistent are the traffic patterns?
- how frequently do we backup the data?
- How long should it take to RESTORE a backup?
- what is the geolocation of most our users?
- is there data / process compliance to be aware of?
- what are the audit requirements?

## NON-FUNCTIONAL

- the system should have 4 nines of availability

- transactions should be backed up daily

- transactions must be encrypted in transit and at rest

- transactions cannot be lost

- every transaction and user action MUST BE AUDITED

Transaction data must be encrypted both in transit and at rest. Additionally, there should be data process compliance requirements to protect PII (Personally Identifiable Information), which may include GDPR compliance depending on the region.

Banking applications are typically read-heavy, meaning users check their balances and transaction history more frequently than they perform writes like transferring money or making payments. Understanding this ratio helps determine appropriate system architecture, caching strategies, and resource allocation.

### What is the tradeoff when implementing end-to-end encryption for transaction data in a microservices architecture?

Normally, HTTPS traffic is decrypted at the edge to make processing faster and avoid computational overhead. However, if data must be encrypted in transit throughout the entire system until it reaches the database, every service must decrypt the data to use it, which is computationally expensive and impacts performance.

### Why are audit requirements considered a non-functional requirement in a banking application?

Audit requirements don't directly affect user-facing functionality, but they determine how the system tracks and logs who performed transactions and when they occurred. This is critical for recovering from issues like lost transactions or investigating fraud, but the user doesn't directly interact with these audit logs.

### three important questions to ask about data durability and backup for a banking system?

How frequently should data be backed up? 2) How frequently should backups be verified/checked? 3) What is the maximum allowed time to restore from a backup? These questions help define availability targets and recovery strategies for the system.

<hr />

# Non-Functional Requirements for URL Shortener

## Questions

- How many MAU's? (Monthly Active Users)
- How many average RPS?
- What is maximum latency allowed?
- What is the maximum length of a URL?
- Do the URL's expire?

## NON-FUNCTIONAL

- redirects should happen in more than 500ms
- system should support 1 million RPS?
- LONG URLs can be at most 3kb
- SHORT URLs can be at most 0.3kb

Setting a maximum URL size is important because it affects database choices and storage considerations.

Without a limit, users could submit garbage data that could take down the system.
Different databases have different limits - object databases have fewer restrictions while relational databases can have stricter limits.

- URL expiration can be considered both functional and non-functional.

It has functional aspects related to feature behavior, but it also affects non-functional considerations like storage and system maintenance - if URLs don't expire, there needs to be a cleanup process, otherwise they will live on forever and impact storage capacity.

### Why should both long and short URLs have size limits in a URL shortener system?

- Both should have size limits to prevent system abuse and ensure predictable storage requirements. Long URLs need limits because databases have storage constraints (relational databases especially) and unlimited size would allow anyone to submit garbage data that could take down the system (e.g., 3 kilobytes). Short URLs also need limits for efficient storage and database constraints (e.g., 1 kilobyte). These limits are important because 'it's the little things that'll take you down' - not checking these constraints is an easy way to take down systems.
