# What Is System Design?

At its core, **System Design** is the process of defining how different parts of a software system interact to meet both **functional** (what it should do) and **non-functional** (how well it should do it) requirements.
It’s not about writing code, at least not yet. It’s about making **high-level architectural decisions** that balance scalability, reliability, performance, and cost

### ==A Real-World Analogy: Designing a Skyscraper==

*Imagine you’re an architect designing a skyscraper.*

*You don’t start by laying bricks. You start by asking questions:*

- *How many floors will it have?*
- *How many people should it support?*
- *What kind of soil is it built on?*
- *What level of earthquake resistance is needed?*

*Once the requirements are clear, you create **blueprints** showing how everything fits together: the foundation, the structural supports, the plumbing, the electrical layout, and the elevator shafts.*

*You also consider how different systems **interact**, such as how plumbing might affect electrical layouts. You plan for **future expansion** (scalability) and think about how the building will handle unexpected issues (fault tolerance).*

In the software world, this translates to:
- **Architecture:** The overall structure of the system. Should the system be built as a monolith, a set of microservices, or an event-driven system?
- **Components/Modules:** Databases, servers, load balancers, caches, message queues, and APIs.
- **Interfaces:** How these components communicate with each other (e.g., REST APIs, gRPC).
- **Data:** How data is stored, managed, accessed, and kept consistent.

# 2. 10 Big Questions of System Design
On a high level, system design revolves around answering these 10 big questions:

1. **Scalability:** How will the system handle a large number of users or requests simultaneously?
2. **Latency and Performance:** How can we reduce response time and ensure low-latency performance under load?
3. **Communication:** How do different components of the system interact with each other?
4. **Data Management:** How should we store, retrieve, and manage data efficiently?
5. **Fault Tolerance and Reliability:** What happens if a part of the system crashes or becomes unreachable?
6. **Security:** How do we protect the system against threats such as unauthorized access, data breaches, or denial-of-service attacks?
7. **Maintainability and Extensibility:** How easy is it to maintain, monitor, debug, and evolve the system over time?
8. **Cost Efficiency:** How can we balance performance with infrastructure cost?
9. **Observability and Monitoring:** How do we monitor system health and diagnose issues in production?
10. **Compliance and Privacy:** Are we complying with relevant laws and regulations (e.g., GDPR, HIPAA)?

![[Pasted image 20251201162845.png]]