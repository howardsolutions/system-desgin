# Asynchronous workflows.

You could accomplish a lot with just asynchronous and caching.

## Asynchronicity

- Helps address the challenge of working with computationally expensive tasks.

- Keeps the system responsive even with long-running tasks.

JavaScript and Node.js are really good at that, but we could use the same mental model at a much larger scale for our system design.

## Expensive task

- Uploading and processing a large video file
- Generating a report
- Processing payments
- Image resizing or thumbnail creation

This could increase the system availability. System availability is not just about our uptime; it's also about how responsive our system is.

## Components

### Message brokers: browse and manage messages, and message queues.

### The message queues: hold messages until a worker is ready to process them.

### Workers: pull jobs from the queue and perform the work.


### EXAMPLES:

Message brokers: Kafka, RabbitMQ

The message queues: RabbitMQ, Amazon SQS.

Worker Management: Kubernetes

## NOTES:

- An asynchronous workflow consists of: 

1) A service/server that creates jobs for long-running tasks, 
2) A message broker that routes and manages messages and queues, 
3) Message queues that hold jobs in a line until workers are available, and 
4) A worker pool that pulls jobs from the queue and executes them. 

The flow is: service creates a job → message broker receives it → job is placed in a queue → available worker pulls and processes the job → worker notifies when complete.

- `Back pressure` is a concept where the system slows down the rate of incoming jobs when queues are filling up faster than workers can process them. 

Instead of letting queues grow indefinitely (which could crash the system), back pressure allows the service to reject new jobs or send errors to clients until the queues clear up, preventing system-wide failures.

- Computationally expensive tasks that would otherwise block system responsiveness are good candidates, including: 
video uploads and processing, image processing, generating reports or PDFs, payment processing, music processing, preparing zip files for download, LLM queries, and image generation. 

These tasks take significant time and would decrease system availability if processed synchronously.

- The most common mistake is overusing async workflows by putting everything into queues. 

While it's tempting because it improves surface-level performance and makes requests return quickly, it adds significant complexity and maintenance overhead. 

Async workflows should only be used when necessary, as they require additional infrastructure (message brokers, queues, worker pools) and make debugging more difficult when things go wrong.

