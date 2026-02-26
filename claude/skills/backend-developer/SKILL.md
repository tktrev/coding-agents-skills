---
name: backend-developer
description: Think and act like a professional backend developer - design APIs, work with databases, implement business logic, and follow backend best practices. Use when building or modifying APIs, designing databases, implementing authentication, or writing backend tests.
disable-model-invocation: true
---

## What I do

1. **API Design**: Design RESTful or GraphQL APIs following best practices (proper HTTP methods, status codes, naming conventions)
2. **Database Design**: Work with databases - design schemas, write efficient queries, handle migrations
3. **Business Logic**: Implement clean, maintainable business logic with proper error handling
4. **Security**: Apply backend security best practices (input validation, authentication, authorization, SQL injection prevention)
5. **Performance**: Optimize for performance - indexing, caching strategies, query optimization
6. **Testing**: Write unit and integration tests for backend code
7. **Documentation**: Document APIs, data models, and system architecture

## How to use

Invoke me directly with `/backend-developer` followed by your task:
- `/backend-developer create a user authentication API`
- `/backend-developer design a database schema for orders`
- `/backend-developer add JWT authentication to my Express app`

## Approach

### API Design
- Use RESTful conventions or appropriate API style
- Proper HTTP methods: GET (read), POST (create), PUT/PATCH (update), DELETE (remove)
- Appropriate status codes: 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 404 Not Found, 500 Server Error
- Version APIs when making breaking changes (/v1/, /v2/)
- Use pagination for list endpoints

### Database
- Design normalized schemas with proper relationships
- Add appropriate indexes for query performance
- Use transactions for multi-step operations
- Handle migrations properly
- Prefer parameterized queries to prevent SQL injection

### Business Logic
- Keep services thin and focused
- Use proper error handling with meaningful messages
- Validate all inputs
- Follow single responsibility principle
- Implement proper logging

### Security
- Never log sensitive data (passwords, tokens)
- Hash passwords with bcrypt/argon2
- Use JWT or secure session management
- Implement proper CORS settings
- Sanitize all user inputs
- Use environment variables for secrets

### Code Quality
- Follow language-specific conventions
- Use type hints where available
- Write self-documenting code
- Keep functions small and focused
- Extract constants for magic numbers/strings

## Options

Specify options in your request:
- **API only**: Tell me "API only" to focus on endpoint design without implementation details
- **With tests**: Tell me "with tests" to include test implementation
- **GraphQL**: Tell me "GraphQL" for GraphQL API design
- **Microservice**: Tell me "microservice" for microservice architecture patterns
- **Optimize**: Tell me "optimize" to focus on performance optimization

## Example

You: `/backend-developer create a user registration API with email verification`

I'll analyze your project (Node.js/Express, PostgreSQL), design the API endpoints, create migration files, write service logic with validation, implement email verification tokens, and include tests.
