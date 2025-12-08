# 01 Foundations

## Hierarchy of Software Architecture Concepts

Think of architecture knowledge as a pyramid:

| Level | Concept | Description | Example |
| --- | --- | --- | --- |
| **Top** | **Software Architecture** | The overall structure of a system: how components interact, constraints, and qualities (scalability, security, performance). | A microservices-based e-commerce platform deployed on Azure. |
| ↓ | **Architectural Styles** | Broad categories of system organization. Defines the "shape" of the system. | Layered architecture, microservices, event-driven, client-server. |
| ↓ | **Architectural Patterns** | Proven solutions to recurring architectural problems. More specific than styles. | CQRS, Saga, API Gateway, Event Sourcing. |
| ↓ | **Design Patterns** | Reusable solutions to common design problems at the code/component level. | Singleton, Factory, Observer, Repository. |
| **Bottom** | **Software Design Principles** | Guidelines for writing maintainable, flexible, and clean code. | SOLID, DRY, KISS, Separation of Concerns. |

## **Hierarchy summary:**

*   **Architecture** (big picture)
    *   **Style** (system shape)
        *   **Pattern** (solution templates)
            *   **Design Pattern** (code-level solutions)
                *   **Principles** (guidelines).

---

## Software Architecture Basics

*   **Definition:** High‑level structure of a software system, defining components, interactions, and constraints.
*   **Goal:** Ensure scalability, maintainability, security, and performance.
*   **Example:** An e‑commerce platform with separate services for catalog, orders, and payments.

---

## Architect Role vs Developer

*   **Developer:** Focuses on implementing features, writing code, and fixing bugs.
*   **Architect:** Focuses on system design, trade‑offs, technology choices, and aligning with business goals.
*   **Example:** Developer implements a payment API; architect decides whether payments are handled via microservices or integrated into a monolith.

---

## Quality Attributes

*   **Scalability:** Handle growth (horizontal scaling).
*   **Availability:** System uptime (99.9% SLA).
*   **Security:** Protect data (OAuth2, Azure AD).
*   **Maintainability:** Easy to update.
*   **Performance:** Fast response times.
*   **Trade‑off Example:** High security may reduce performance due to encryption overhead.

---