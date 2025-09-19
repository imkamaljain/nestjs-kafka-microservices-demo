# NestJS Microservices Project

This is a microservices architecture project built with NestJS and managed with Nx workspace.

## Project Structure

- `apps/api-gateway` - Main entry point that routes requests to appropriate services
- `apps/notification-ms` - Service for handling notifications
- `apps/order-ms` - Service for managing orders
- `apps/payment-ms` - Service for processing payments

Each service has its corresponding end-to-end tests in a separate directory (e.g., `order-ms-e2e`).

## Prerequisites

- Node.js (version 16 or higher)
- npm or yarn

## Installation

1. Clone the repository
2. Install dependencies:
```bash
npm install
```

## Running the Project

To start all services:

```bash
npx nx run-many --target=serve --all
```

This will start all microservices and the API gateway.

To start a specific service:

```bash
npx nx serve api-gateway
npx nx serve order-ms
npx nx serve payment-ms
npx nx serve notification-ms
```

## Testing

To run tests for all services:

```bash
npx nx run-many --target=test --all
```

To run tests for a specific service:

```bash
npx nx test order-ms
```

## Building

To build all services:

```bash
npx nx run-many --target=build --all
```

To build a specific service:

```bash
npx nx build order-ms
```

## Technology Stack

- **NestJS** - A progressive Node.js framework for building efficient and scalable server-side applications
- **Nx** - Smart build system with monorepo support
- **TypeScript** - Typed superset of JavaScript
- **Kafka** - Used for communication between microservices

## Architecture

This project follows a microservices architecture where each service is responsible for a specific business domain:
- API Gateway handles incoming requests and routes them to appropriate services
- Order service manages order creation and processing
- Payment service handles payment processing
- Notification service sends notifications to users

Services communicate with each other through Kafka messaging system.