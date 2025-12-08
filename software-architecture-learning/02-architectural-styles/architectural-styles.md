# Architectural Styles

Architectural styles are **high‑level system organization approaches** that define how components are structured and interact. They sit above architectural patterns and design patterns in scope. Below is a **complete list of major architectural styles** with details, scope, and examples.

## Comprehensive List of Software Architectural Styles

| Style | Description | Scope | Example |
| --- | --- | --- | --- |
| **Layered (N‑tier)** | Organizes system into layers (presentation, business, data). Each layer only interacts with the one below. | Entire application/system | Classic ASP.NET MVC app with UI, service, and repository layers. |
| **Microservices** | System decomposed into small, independent services communicating via APIs. | Suite of applications | E‑commerce platform with catalog, payment, shipping microservices on Azure Kubernetes Service. |
| **Serverless** | Functions triggered by events, managed by cloud provider. | Application/system | Azure Functions handling image uploads. |
| **Client–Server** | Splits system into clients (requesters) and servers (providers). | Application/system level | Angular front‑end consuming .NET Web API. |
| **Publish–Subscribe** | Components subscribe to topics; publishers broadcast messages. | Subsystem/system | Azure Service Bus topics for order notifications. |
| **Event‑Driven** | Components communicate via events; decoupled producers and consumers. | System or subsystem | IoT telemetry ingestion using Azure Event Hub. |
| **Microkernel (Plug‑in)** | Core system with plug‑in modules for extensibility. | Application level | Eclipse IDE with plug‑in architecture. |
| **Domain‑Driven (DDD style)** | Organizes system around business domains and bounded contexts. | Enterprise application/system | Insurance system with bounded contexts for claims, policies, billing. |
| **Service‑Oriented (SOA)** | Services expose functionality via contracts; often enterprise‑scale. | Enterprise suite | Legacy enterprise apps using SOAP services. |
| **Space‑Based (Cloud/Grid)** | Eliminates database bottlenecks by distributing data and processing across nodes. | Large distributed systems | High‑volume trading system using in‑memory data grids. |
| **Pipe‑and‑Filter** | Data flows through a sequence of processing components (filters). | Subsystem or application | Compiler architecture: lexical analysis → parsing → code generation. |
| **Data‑Centered (Repository/Blackboard)** | Central data store accessed by multiple components. | Application/system | Blackboard architecture in AI systems; shared database in ERP. |
| **Peer‑to‑Peer (P2P)** | All nodes act as both clients and servers. | Network/system | BitTorrent file sharing. |
| **Hexagonal (Ports & Adapters)** | Core logic isolated from external systems via ports/adapters. | Application level | Clean architecture in .NET Core with adapters for DB and APIs. |
| **Layered + Modular Hybrid** | Combines layered separation with modular plug‑ins. | Application/system | ERP system with layered core and modular extensions. |