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