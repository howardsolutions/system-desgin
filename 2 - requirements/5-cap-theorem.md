# CAP THEOREM

# QUALITY

## RELIABILITY

The ability for the system to `function correctly OVERTIME`

It's considered key because even at 90% uptime, for large-scale systems like Google with millions of users
the downtime affects a significant number of people.

The 'over time' aspect is critical—anyone can build a system that works for a short period, but maintaining functionality over long periods with millions of users is what matters.

### AVAILABILITY

the `proportion of time` a system is `operational and accessible`.

### RESILIENCY

How well does the system handle `failures`?

### CONSISTENCY

How well does the system ENSURE that all users see the SAME DATA at the SAME TIME?

<hr />

## CAP THEOREM

### 1. CONSISTENCY = every read receives the most recent write or error

### 2. AVAILABILITYs = every request receives a (non-err) response

### 3. PARTITION TOLERANCE = The system continues to OPERATE even if messages are delayed or lost.

## ANY DISITRIBUTED SYSTEM can ONLY guarantee 2 OUT OF 3 AT THE SAME TIME.

- In distributed systems, network failures WILL HAPPEN.

- YOU MUST DECIDE: is it more important to have the LATEST DATA (consistency) OR to always be AVAILABLE be up more of the time (availability)

- There's NO "PERFECT" SYSTEM. Trade-offs are necessary.

- CAP theorem describes the trade-offs in distributed systems between Consistency, Availability, and Partition tolerance.
  It states that a distributed system can only guarantee 2 out of these 3 properties at the same time.

- In practice, since partition tolerance (handling network failures and errors) CANNOT BE AVOIDED in distributed systems, the real choice is between consistency and availability—you must sacrifice one to handle partitions.

- Partition tolerance (the ability to handle network failures and errors) cannot be eliminated in distributed systems—errors will inevitably happen when dealing with millions or billions of events.

Since partition tolerance must be assumed, the real choice is between consistency and availability. A system can be consistent and partition-tolerant, or available and partition-tolerant, but not all three simultaneously.

### How is availability measured in distributed systems?

Availability is measured as the proportion of time a system is operational and accessible. It's calculated as a real metric/formula based on uptime and downtime, and is typically expressed as a percentage, often referred to in terms of 'nines' (4 nines = 99.99%, 5 nines = 99.999%, etc.).

## EXERCISE OF MAKING TRADE-OFFS

1. banking app: much important to be consistency & partition tolerance THAN AVAILABILITY all the time.

2. URL SHORTENING SERVICE: AVAILABILITYs & partition tolerance. because the links need to be up most of time pp need click to
   The core functionality is connecting people with the short code to the destination URL, so the service must be able to handle requests and be accessible to users at all times.

3. an online luxury banana store: most critical facor is the transaction -> choose consistency > availability

4. medical team todo app:
   doctors and nurse need to see the most up-to-date patient all the time.

=> availability

5. social todo app for friends, friends share a lists for planning a party

social app is bias toward more READ than WRITE.

=> AVAILABILITYs
