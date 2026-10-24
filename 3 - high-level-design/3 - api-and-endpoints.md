# APIs and Endpoints

- APIs should be a literal translation of business requirements into code. If you can successfully convert functional and nonfunctional requirements into an API, most of the work is already done for a simple application.

- Consider the `complexity and expense` of the operation.
  For example, an expensive calculation like comparing multiple stock ticker symbols would warrant a `separate` endpoint rather than lumping it together with other operations.

- You should focus on what's the simplest, cheapest thing you can do, rather than automatically choosing the most rigorous or overengineered solution. Avoid unnecessary complexity when a simpler approach will suffice.

- Listing out endpoints helps visualize the actual scope of the system. It can reveal that complex functional requirements may boil down to just a few endpoints, making the system easier to reason about and understand.

- When the API is simple enough that it doesn't merit the added complexity.
  If the system only requires a few straightforward endpoints, a simpler REST-based approach may be more appropriate than introducing GraphQL.
