# go-advanced-lessons
This repository contains source code for the Go programming video series on my YouTube channel, The Art of Development.
Watch on YouTube https://www.youtube.com/channel/UCkeO0vkJAu74LaNud9j89aw

---

### 1.  Architecture
The project uses a layered architecture with some DDD elements.  
Layers:
- **Handler (Transport Layer):** HTTP request handling, route registration.
- **Service (Business Logic Layer):** business logic, works with repositories.
- **Repository/Storage (Data Access Layer):** data access (PostgreSQL, MongoDB).
- **Model/DTO:** data structures for inter-layer communication.

---

### 2. Used Patterns
- **Repository:** abstraction for data access (interfaces and PostgreSQL implementations).
- **Service:** encapsulates business logic.
- **DTO (Data Transfer Object):** structures for data transfer between layers.
- **Middleware:** error handling, sorting, logging.
- **Manual Dependency Injection:** dependencies passed via constructors.
- **Singleton (Config):** config loaded once via sync.Once.

---

### 3. Drawbacks & Problems
- **No unit/integration tests:** no `_test.go` files, making logic verification harder.
- **Partial CRUD implementation:** Update/Delete methods in repositories are not implemented (panic).
- **Weak data validation:** no explicit input validation.
- **Tight coupling to concrete implementations:** services/handlers are tightly bound to specific repository implementations.
- **No clear domain package separation:** folder structure is complex but not pure DDD.
- **No performance or load tests.**
- **No documentation for setup/environment.**
- **No business logic error handling (only HTTP level).**
