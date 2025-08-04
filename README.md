# NestJS Learning Project

<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

## Description

A learning project exploring NestJS framework capabilities, built while comparing it to FastAPI (Python). This project demonstrates core NestJS features including database integration, API design patterns, validation, rate limiting, and logging.

## Features

- **RESTful APIs**: User and Employee management endpoints
- **Database Integration**: PostgreSQL with Prisma ORM
- **Data Validation**: DTOs with class-validator
- **Rate Limiting**: Configurable throttling with @nestjs/throttler
- **Custom Logging**: Structured logging service
- **Database Migrations**: Prisma migrations setup
- **Testing**: Unit and e2e test configurations

## API Endpoints

### Users
- `GET /users` - Get all users (with optional role filter)
- `GET /users/:id` - Get user by ID
- `POST /users` - Create new user
- `PATCH /users/:id` - Update user
- `DELETE /users/:id` - Delete user

### Employees
- `GET /employees` - Get all employees (with optional role filter)
- `GET /employees/:id` - Get employee by ID
- `POST /employees` - Create new employee
- `PATCH /employees/:id` - Update employee
- `DELETE /employees/:id` - Delete employee

## Tech Stack

- **Framework**: NestJS
- **Database**: PostgreSQL
- **ORM**: Prisma
- **Validation**: class-validator & class-transformer
- **Rate Limiting**: @nestjs/throttler
- **Testing**: Jest
- **Language**: TypeScript

## Project Structure

```
src/
├── users/           # User module (CRUD operations)
├── employees/       # Employee module (CRUD with Prisma)
├── database/        # Database service and configuration
├── my-logger/       # Custom logging service
└── dto/            # Data Transfer Objects
```

## Prerequisites

- Node.js (v16 or higher)
- PostgreSQL database
- npm or yarn

## Environment Setup

Create a `.env` file in the root directory:

```env
DATABASE_URL="postgresql://username:password@localhost:5432/your_database?schema=public"
```

## Installation

```bash
# Install dependencies
$ npm install

# Generate Prisma client
$ npx prisma generate

# Run database migrations
$ npx prisma migrate dev
```

## Running the Application

```bash
# Development mode
$ npm run start:dev

# Production mode
$ npm run start:prod

# Debug mode
$ npm run start:debug
```

The application will be available at `http://localhost:3000`

## Database Management

```bash
# Create new migration
$ npx prisma migrate dev --name your_migration_name

# Reset database
$ npx prisma migrate reset

# View database in Prisma Studio
$ npx prisma studio
```

## Testing

```bash
# Unit tests
$ npm run test

# Watch mode
$ npm run test:watch

# Test coverage
$ npm run test:cov

# E2E tests
$ npm run test:e2e
```

## Rate Limiting

The application includes rate limiting configured with two tiers:
- **Short**: 3 requests per second
- **Long**: 100 requests per minute

## Learning Notes

This project was created to explore NestJS features and compare them with FastAPI patterns:

- **Decorators vs Decorators**: Both frameworks use decorators extensively
- **Dependency Injection**: NestJS has built-in DI, similar to FastAPI's depends
- **Validation**: NestJS uses class-validator, FastAPI uses Pydantic
- **Database**: NestJS with Prisma vs FastAPI with SQLAlchemy/Tortoise
- **Middleware**: Both support middleware patterns for cross-cutting concerns

## License

This project is for learning purposes and is not licensed for commercial use.

## Author

Built while learning NestJS and comparing it to FastAPI patterns.