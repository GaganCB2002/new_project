# Testing Guide

## Current State
- Minimal unit tests exist in the `test/` directory for backend services.
- Postman collections are used for API validation.

## Missing Tests
- Comprehensive Frontend component tests (Jest/React Testing Library).
- End-to-End (E2E) UI testing.

## Recommended Strategy
- **Unit Testing:** Implement Jest for Node.js and JUnit for Spring Boot. Target 80% coverage on business logic (Payroll, Auth).
- **Integration Testing:** Test database queries and Kafka message production.
- **E2E Testing:** Use Cypress or Playwright to simulate full user journeys (Login -> Clock In -> View Tasks).
