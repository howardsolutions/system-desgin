# NON-FUNCTIONAL REQUIREMENTS

- how many users do we expect?
  what is the average RPS? (request per second)
  does this number change over time?

- how consistent does the system need to be?
  is it acceptable for users to see slightly outdated data

- what metrics are important?
  what is the maximum latency?

- what data needs to be protected?

- Non-functional requirements are about understanding and targeting system quality attributes such as consistency, availability, and partition tolerance (fault tolerance).
  They help determine which aspects of system quality are most important for a given system by answering questions about expected users, response times, and other quality metrics.

- The number of users may not always be the most important metric. For some systems, like a URL shortening service, the requests per second is more important than the raw user count.
  Understanding traffic patterns and request volumes helps properly scale the system to handle the actual load rather than just focusing on user numbers.

### What is the performance tradeoff when implementing HIPAA compliance requirements for medical data?

- HIPAA compliance requires that data be encrypted at rest, meaning the database must go through a series of security checks for every single request. This encryption and decryption process makes the system slower. Additionally, when encrypted databases need to communicate with other databases, they must also perform these security operations, adding complexity and further reducing performance.

- Product teams tend to provide their maximum expected user count for the product's lifetime, which may not be reached until years after launch.
  This can lead to over-scaled systems that are designed for peak loads that won't occur for a long time.

  Understanding the timeline and growth pattern helps design systems that can scale up and down appropriately, avoiding unnecessary infrastructure costs early on.
