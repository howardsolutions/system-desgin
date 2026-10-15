# Everything is a System

- A System is a COLLECTION OF COMPONENTS THAT WORK TOGETHER to SOLVE a problem.

- It should have a defined input, output, boundaries or constrain its scope.

## Three essential characteristics that a system or component should have

1. Input
2. Output
3. Boundaries

These characteristics help define what the system does and what scope it operates within

- Boundaries are important to prevent scope creep and to constrain the problem space.
  Without boundaries, systems are endless and you could spend infinite time going deeper into details.

Boundaries help FOCUS on what is important and prevent getting lost in areas that may not be relevant to the actual problem being solved.

## Understanding your role in the system and how the parts around you interconnect makes you more effective.

Recognizing what different teams and roles do, and how they CONNECT, allows you to work more efficiently and make better decisions about WHERE to FOCUS your efforts.

## 2 SYSTEMS with the SAME COMPONENTS could produce vastly DIFFERENT RESULTS.

While systems may have the same high-level components.
it's the details and nuances of those components, and how they work together,
that determine the actual performance and characteristics of the system.

The same basic parts can be optimized and configured differently to serve completely different purposes.

## Notes on the Exercise design a pizza shop

- It's acceptable that different people produce different diagramss
  because initial requirements are often vague, and people have different perspectives and experiences that inform their approach.

As long as the solution makes logical sense and can be explained, and the end goal is achieved (like the customer getting their pizza), the design is valid.

### key skills involved in system design of a business processs

- Breaking down requirements into logical steps, thinking critically about what needs to be accomplished, and identifying what details are necessary versus what can be abstracted away.

This involves asking the RIGHT QUESTIONS to CLARIFY requirements before designing the system.

- Product managers typically care about features being built, requirements, accessibility, supported languages, and high-level architectural decisions.
  They usually don't care about implementation details like whether TypeScript or JavaScript is used.

- Without detailed requirements and asking the right questions
  you'll make assumptions that may not align with what's actually needed.

Different stakeholders care about different details - for example, a product manager likely cares about features, requirements, accessibility, and supported languages, but probably not whether you use TypeScript or JavaScript.

## What is a Distributed System

- Multiple computers working together as a SINGLE SYSTEM

- Components maybe PHYSICALLY SEPARATED

- Designed to handle FAILURES and SCALE across multiple locations.

- Distributed systems are created to handle failure and to be able to scale.
  It's difficult to scale just one machine (vertical scaling), and a single machine creates a single point of failure. By distributing across multiple machines, systems can better handle load and avoid catastrophic failures.


## COMMON SYSTEM COMPONENTS

1. Client - Role: sends requests, displays data to users.

2. Database - Stores, updates and retrieves data

3. Server - Process requests, business logic.

4. Load balancer - Distributes INCOMING traffic to keeps things running smoothly

5. Cache - Make things FASTER by TEMPORARILY storing data

you don't always NEED to cache, but you should always be caching.

ABC = always be caching.

cache makes things faster. we always want cache WHEN we can.
