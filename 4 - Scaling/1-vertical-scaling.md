# SCALING

## Vertical scaling: ADD MORE POWER

- Increase performance by adding more power (CPU, RAM, GPU, etc) to a machine

PROS: simple to implement, no code changes required, easier to maintenance

CONS: physical limits of hardware, expensive to scale up / down, decreased resiliency

## Horizontal scaling: MORE MACHINES

Horizontal scaling introduces increased complexity and operational overhead. With multiple machines, you need orchestration systems to manage them all, which can require specialized software like Zookeeper or distributed messaging systems to handle the complexity of distributed systems.

With vertical scaling and only a few large servers, if one server goes down, it represents a large portion of your total capacity. This creates a single point of failure risk, whereas horizontal scaling distributes the load across many servers, so losing one server has less impact.
