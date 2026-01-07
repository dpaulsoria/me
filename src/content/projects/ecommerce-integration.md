---
title: "E-commerce Platform (Private Contract)"
description: "E-commerce built from scratch: React frontend + Node/Express API + MySQL, integrating billing, e-signing and payments, plus a recurring billing worker."
stack:
  - "React"
  - "React Router (routing)"
  - "Node.js"
  - "Express"
  - "MySQL"
  - "Payment gateway (webhooks + idempotency)"
  - "Billing/Invoicing integration"
  - "E-signature / contract automation integration"
  - "Background worker (recurring charges)"
date: "2022-01-01"
featured: false
order: 10
---

> Note: This was a private contract project. The repository and UI screenshots are not public due to confidentiality and access removal after delivery.

## Problem
A client needed an e-commerce platform built from scratch with:
- Standard online sales flow (catalog, cart, checkout, orders).
- Automated invoices through a billing system.
- Automated contract generation + e-signature.
- Online payments (card) plus recurring charges for subscription-like purchases.

## What I built
### Backend (Node/Express)
- API for products, customers, orders, payments and post-payment automation.
- Integration layer using adapters for external services (billing, e-signing, payment gateway).
- Webhook processing for payment events (paid/failed/refunded) with idempotency and safe retries.
- Recurring billing worker (scheduled job) to run charges, handle failures and flag/notify accounts.
- Operational tooling: audit logs/events persisted for traceability.

### Frontend (React)
- Built reusable UI templates/components for the storefront/admin sections.
- Implemented key screens (e.g., product listing/details, cart/checkout, order status).
- Set up client-side routing (React Router) and basic route protection/guards for private areas.
- Integrated frontend flows with the backend API (loading states, error handling patterns).

## Architecture
- React consuming a REST API.
- Express API with layered structure:
  - Routes/controllers (HTTP)
  - Services (business logic)
  - Integration adapters (external APIs)
  - Repositories (DB access)
- MySQL for core entities (orders, payments, subscriptions, audit logs).
- Background job for recurring billing + retry strategy.
- Webhook endpoint with:
  - signature validation
  - idempotency keys
  - event persistence (audit trail)

## Challenges & tradeoffs
- Payment consistency: webhooks can arrive late/duplicated → idempotent handlers + event history.
- Retries without double-charging: simple state machine for attempts + backoff.
- External API downtime/rate limits: controlled retries + logs for investigation.
- Keeping frontend shipping fast while maintaining a clean backend/integration boundary.

## Results / Impact
- Delivered end-to-end e-commerce flow with automated billing + contract signing.
- Reduced manual operations by automating post-payment tasks and recurring charges.
- Improved traceability with audit logs and persisted payment events.

## What can be improved later?
- Add a proper queue system (e.g., BullMQ/RabbitMQ) for background processing at scale.
- Increase test coverage (unit + integration tests for webhooks/adapters + UI flows).
- Add observability (structured logs, metrics, alerts, tracing).
- Containerized local setup (Docker Compose) + CI checks.
