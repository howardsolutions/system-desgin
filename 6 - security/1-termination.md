# TERMINATION

## What is the purpose of HTTPS in system security, and why is it generally terminated at certain points rather than maintained throughout the entire request path

HTTPS encrypts data during transit, like putting data in an armored car.

It's generally terminated (decrypted) at certain points like load balancers or API gateways because keeping the connection encrypted throughout would be slow and unwieldy - every server along the way would need to inspect the encrypted request.

Termination requires a certificate at each termination point to decrypt the traffic.

However, for compliance scenarios (HIPAA, financial transactions) or highly sensitive data, encryption may need to be maintained throughout the entire path to prevent any intermediate service from reading the data, despite the computational cost.

The decision involves trading off efficiency against security requirements.

## Why is encryption and decryption considered computationally expensive, and when might this become a performance concern?

All cryptography is computationally expensive by nature - that's why encryption algorithms like SHA-512 are difficult to break.

While encryption/decryption costs are negligible at small scale, at millions of requests per second, the overhead of encrypting and decrypting can significantly slow down servers and become a performance bottleneck that needs to be addressed.

## What are three strategies for SSL/TLS termination in a distributed system?

1. Terminate at the load balancer or API gateway/reverse proxy — the most common approach.

2. Terminate at the application level, where the load balancer proxies the encrypted request all the way through to the service that actually needs it, which then decrypts it.

This is used for highly sensitive data like HIPAA or financial transactions where the data must stay encrypted the entire way through.

3. Terminate at the load balancer, read the request, and let the load balancer decide whether to re-encrypt sensitive information before forwarding it or route it unencrypted — less common and computationally expensive.

## In what scenarios would you want to keep data encrypted throughout the entire request path until it reaches the final service, rather than terminating SSL/TLS at the load balancer?

When dealing with highly sensitive data that requires compliance (such as HIPAA for healthcare or financial/banking transactions), you should keep encryption throughout the entire path. 

This prevents any intermediate services along the way from reading the traffic, protecting against potential bad actors within the company who might access or modify the data. 

It ensures that `only the final destination service` can decrypt and read the sensitive information.

## What security risk do logging services pose in a system that terminates SSL/TLS early in the request path?  

Logging services often make copies of requests, including their payloads. 

If SSL/TLS is terminated early and requests contain private or financial information, the log database will contain unencrypted sensitive data that most people can access. 

This creates a large exposed database of private information that shouldn't be there. 

Logs must be carefully cleaned to remove sensitive information like passwords and personal data.

