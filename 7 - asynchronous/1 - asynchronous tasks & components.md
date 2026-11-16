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

