# VybeFest API

A Java 21 and Spring Boot backend for a single-festival ticketing platform. This is an independent portfolio project inspired by festival ticketing workflows; it is not affiliated with Solfest.

## Current milestone

The initial application shell exposes a JSON health endpoint at `GET /api/v1/health`. The catalogue, authentication, bookings, payments, tickets, check-in, PostgreSQL persistence, and Kafka workflow will be added as small working slices.

## Technology

- Java 21
- Spring Boot 3.5
- Maven
- PostgreSQL (planned as the source of truth)
- Apache Kafka (planned for asynchronous post-payment processing)

## Run locally

Install Maven 3.6.3 or later, then run:

```powershell
mvn spring-boot:run
```

Open `http://localhost:8080/api/v1/health`. Spring Boot Actuator also exposes `http://localhost:8080/actuator/health`.

## Project principles

- Build one complete booking-to-ticket flow before adding optional features.
- Keep PostgreSQL authoritative for bookings, payment state, inventory, and tickets.
- Use Kafka for asynchronous follow-up work, with duplicate-safe consumers.
- Keep payment processing in sandbox mode for this MVP.
