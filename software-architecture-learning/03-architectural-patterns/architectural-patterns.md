# Architectural Patterns

## 1\. Monolithic & Layered Patterns

Focus on internal organization and deployment simplicity.

| Pattern | Description |
| --- | --- |
| **Monolithic** | Single deployable unit; tightly coupled components. |
| **Modular Monolith** | One deployment, but internally modularized for maintainability. |
| **Layered (N-Tier)** | Organized into layers: Presentation → Business → Data. |
| **Three-Tier Architecture** | UI, Application Logic, and Database tiers. |
| **MVC / MVVM / MVP** | UI-centric patterns for organizing presentation logic. |

---

## 2\. Client–Server & Distributed Patterns

Define how components communicate across networks.

| Pattern | Description |
| --- | --- |
| **Client–Server** | Clients request services from centralized servers. |
| **Peer-to-Peer (P2P)** | Nodes act as both clients and servers. |
| **Service-Oriented Architecture (SOA)** | Services communicate via ESB/SOAP. |
| **Microservices** | Independently deployable services communicating via APIs. |
| **Self-contained Systems (SCS)** | Independent web apps linked via APIs. |

---

## 3\. Component-Based & Modular Patterns

Focus on extensibility and internal separation of concerns.

| Pattern | Description |
| --- | --- |
| **Microkernel (Plug-in)** | Core system with extensible plug-ins. |
| **Hexagonal (Ports & Adapters)** | Isolates core logic from external systems. |
| **Onion Architecture** | Layers wrapped around domain model. |
| **Clean Architecture** | Entities → Use Cases → Adapters → Frameworks. |

---

## 4\. Event-Driven & Message-Oriented Patterns

Enable asynchronous and reactive communication.

| Pattern | Description |
| --- | --- |
| **Event-Driven Architecture (EDA)** | Components communicate via events. |
| **Publish–Subscribe** | Subscribers receive updates when events are published. |
| **Message Broker / Queue-Based** | Async communication via Kafka, RabbitMQ, etc. |
| **Pipes and Filters** | Data processed through sequential steps. |

---

## 5\. Domain & Data-Centric Patterns

Focus on modeling business logic and managing data flow.

| Pattern | Description |
| --- | --- |
| **Domain-Driven Design (DDD)** | Structure around business domains. |
| **CQRS** | Separate read and write models. |
| **Event Sourcing** | Persist state as a series of events. |
| **Repository** | Abstracts persistence logic. |

---

## 6\. Cloud & Deployment Patterns

Optimize for cloud-native, scalable, and resilient deployments.

| Pattern | Description |
| --- | --- |
| **12-Factor App** | Principles for building SaaS/cloud-native apps. |
| **Serverless / FaaS** | Functions run without managing servers. |
| **Sidecar** | Helper container deployed alongside a service. |
| **Ambassador** | Proxy for outbound service requests. |
| **Adapter (Infra)** | Standardizes service interfaces. |
| **Strangler Fig** | Incrementally replace legacy systems. |
| **Service Mesh** | Dedicated layer for microservice communication. |

---

## 7\. Resilience & Distributed Transaction Patterns

Ensure fault tolerance and consistency in distributed systems.

| Pattern | Description |
| --- | --- |
| **Circuit Breaker** | Prevent cascading failures. |
| **Bulkhead** | Isolate failures in system components. |
| **Saga** | Manage distributed transactions across services. |
| **Retry/Timeout** | Improve reliability in remote calls. |

---

## 8\. Presentation & Interaction Patterns

These patterns focus on organizing UI logic and user interaction.

| Pattern | Description |
| --- | --- |
| **MVC (Model–View–Controller)** | Separates data (Model), UI (View), and logic (Controller). |
| **MVVM (Model–View–ViewModel)** | Common in WPF/.NET; ViewModel binds UI to Model. |
| **MVP (Model–View–Presenter)** | Presenter handles UI logic, more testable than MVC. |

---

## 9\. Integration Patterns

These patterns facilitate communication and orchestration across services and systems.

| Pattern | Description |
| --- | --- |
| **API Gateway** | Unified entry point for APIs; handles routing, auth, rate limiting. |
| **Aggregator** | Combines results from multiple services into one response. |
| **Backend-for-Frontend (BFF)** | Tailored backend per UI (e.g., mobile vs web). |
| **Adapter / Anti-Corruption Layer (ACL)** | Bridges legacy and modern systems. |

> Often used in **Microservices**, **SOA**, and **Strangler Fig** transitions.

---

## 10\. Security Patterns

These patterns enforce authentication, authorization, and trust boundaries.

| Pattern | Description |
| --- | --- |
| **Zero Trust Architecture** | No implicit trust; verify every access. |
| **Identity Provider (IdP) + Federation** | Centralized auth via OAuth2, OpenID Connect. |
| **Policy Enforcement Point (PEP)** | Middleware enforcing access control policies. |

> These patterns are critical in **cloud-native**, **multi-tenant**, and **enterprise** systems.

---

## 11\. Data Management & Storage Patterns

These patterns optimize data access, consistency, and scalability.

| Pattern | Description |
| --- | --- |
| **Database per Service** | Each microservice owns its data store. |
| **Shared Database** | Multiple services access a common database. |
| **Sharding & Partitioning** | Split data across nodes for scalability. |
| **Caching Layers** | Use cache (e.g., Redis) to boost performance; often paired with CQRS. |

> These patterns are essential in **Microservices**, **CQRS**, and **Event Sourcing** contexts.

# TODO Update/merge below content

### Integration Patterns

*   **API Gateway:** Single entry point for clients. Example: Azure API Management.
*   **Event Sourcing:** Store events instead of state. Example: Order history logs.
*   **Message Broker:** Decouple services via messaging. Example: Azure Service Bus.

### Data Patterns

*   **CQRS:** Separate read/write models. Example: Queries via SQL, commands via events.
*   **Repository:** Abstract data access. Example: EF Core repository layer.
*   **Unit of Work:** Manage transactions across repositories.

### Cloud Patterns

*   **Circuit Breaker:** Prevent cascading failures. Example: Polly in .NET.
*   **Retry:** Automatic retries on transient errors.
*   **Autoscaling:** Scale services based on load. Example: Azure App Service autoscale.
*   **Sharding:** Split database horizontally. Example: Cosmos DB partitions.

# Design Patterns & Architectural Patterns

| Aspect | Design Patterns | Architectural Patterns |
| --- | --- | --- |
|   | The **details inside components** (class/object interactions) | The **big picture** (system structure) |
| **Level of abstraction** | Low-level (class, object, module) | High-level (system, application, enterprise) |
| **Scope** | Solves programming/design issues | Solves architectural/system issues |
| **Focus** | Code reuse, flexibility, maintainability | System organization, scalability, performance |
| **Change impact** | Easier to refactor if wrong | Harder/costly to change later |
| **Concerns** | How classes interact & responsibilities | How components/subsystems are structured & interact |
| **Examples** | GoF, Singleton, Factory, Observer, Strategy | Layered, Microservices, Client–Server, Event-Driven, CQRS |