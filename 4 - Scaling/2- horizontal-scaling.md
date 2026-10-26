# HORIZONTAL SCALING

- Increase performance by adding MORE machines

## PROS:

- easily scales up / down with traffics.
- high availability
- increased fault tolerance

## CONS:

- requires orchestration
- can require code changes

# LOAD BALANCERS / Reverse Proxy

- distributes traffic evenly across services

- can act as a gateway for routing

- handles health checks and failovers

- A reverse proxy, such as Nginx, can perform load balancing along with many other functions including HTTPS termination, route-based routing with deeper inspection, and health checks.

While dedicated load balancers exist for very high traffic applications (like Amazon Elastic Load Balancer), reverse proxies generally offer more flexibility.

In system design discussions, the terms are often used interchangeably unless specific functionality needs to be clarified.

## TAKEAWAYS

- high-level design is about focusing on the main components and their interactions.

- Scaling means trade-offs. Vertical scaling is easier but has limits. Horizontal scaling increase the flexibility but requires more operational overhead.

### When scaling a simple application from one server to three servers, what unexpected bottleneck might be discovered?

- The database might become the bottleneck if it's not scaled accordingly. Additionally, load balancing becomes a critical issue - the client needs a way to distribute requests across multiple servers and handle situations where servers go offline. What was previously a simple direct connection to one server now requires coordination. These bottlenecks may have been masked by the single server's limitations.

### Why do distributed systems typically start with horizontal scaling by default rather than adopting it later?

Starting with horizontal scaling from the beginning avoids the need to refactor code later.

When moving from vertical to horizontal scaling, code must be refactored because APIs that were previously on the same machine may now be on different machines, which changes latency and requires architectural adjustments to handle distributed components.

### For a read-heavy database application, what component is typically placed in front of the database to improve performance and handle 100,000+ users?

A cache is typically placed in front of the database for read-heavy applications to improve performance and handle high user loads.

### When sketching a system architecture diagram, how can you represent multiple servers in a cluster without drawing each individual server?

You can draw a container around a few server instances to imply that it's a cluster. This convention indicates there are multiple servers (potentially 20, 30, or 50) without having to sketch out each one individually.

### In a system architecture diagram with multiple boxes and arrows, what practice helps clarify the purpose of each component?

Labeling what each component is doing helps clarify the system. For example, noting that the load balancer is doing routing, or that the web server is handling business logic and API requests.

- Load balancers can also be positioned in front of multiple databases, though this addresses a different type of problem related to database distribution.
