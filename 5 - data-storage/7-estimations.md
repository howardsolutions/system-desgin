# Estimations

- Help Ground Vague requirements in reality
- Must think about specific system components
- Show interviewer thought process
- Do not have to be precise

# Strategy

Structured Notes:

1. Clarity
   - A: Identify what is being estimated (e.g., user storage requests).
   - B: Ask questions or make reasonable assumptions (e.g., number of users).
   - C: Validate assumptions by write them down.
2. Do the math.
3. Sanitize and check your results.

## Software Engineering Principles:

- Avoid making assumptions
- Maintain binary logic (right or wrong)

# NOTES

- Estimations help determine if you're in the right ballpark for system requirements and help identify what needs to be measured (traffic patterns, users, RPS, storage).
  They provide a sanity check and help understand the most important aspects of the system, such as identifying bottlenecks.
  `The goal is direction rather than precision.`

- The key metrics to estimate include: number of users, requests per second (RPS), and storage capacity needed.
  You should `focus on estimating the most important thing` that will become a bottleneck in your system, such as redirects for a URL shortener or database storage for a to-do app.

- a reasonable maximum size for a single database before considering sharding or partitioning?

Anything under 500 gigabytes provides a lot of margin for a single database.

Around a terabyte, you might start thinking about sharding. Generally, if you're dealing with a couple hundred gigabytes, you're safe with a single database. The scale of terabytes per month would automatically suggest needing multiple databases.

# When calculating storage requirements for a to-do app with 100,000 users, assuming 500 bytes per task, 3 tasks per day, and 30 days per month, approximately how much storage is needed per month?

Using these assumptions: 100,000 users × 3 tasks/day × 30 days × 500 bytes = 4,500,000,000 bytes ≈ 4.5 GB per month.

This demonstrates that even at this scale, storage requirements are manageable for a single database. Databases can typically handle several hundred gigabytes without requiring sharding or partitioning, so you have significant margin at this level of usage.

- You should know that in-memory storage is faster than disk, and cache is faster than database. While you don't need to memorize precise timings for L1 cache, L2 cache, or exact lookup times, understanding these relative speed relationships is sufficient for making reasonable system design decisions.
