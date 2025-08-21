## API
> A short and comprehensive guide to API fundamentals, structure, and best practices
- What is an API?
> An API (Application Programming Interface) is a set of rules and protocols for building and interacting with software applications. It defines the methods and data formats that applications can use to communicate with each other.

All fundamental API concepts

<div id="top"></div>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### 📋 Table of Contents

| Section | Topic | Description | Priority |
|---------|-------|-------------|----------|
| **FOUNDATIONS** | | | |
| 1 | [API Basics](#api-basics) | Overview of API concepts, terminology, and why APIs matter |  Critical |
| 2 | [Types of APIs](#types-of-apis) | REST, SOAP, GraphQL, WebSockets, RPC, gRPC |  Critical |
| 3 | [HTTP Protocol Deep Dive](#http-protocol-deep-dive) | Request/response cycle, headers, status codes, content negotiation |  Critical |
| 4 | [HTTP Methods](#http-methods) | GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD - when and how to use |  Critical |
| 5 | [Data Formats and Serialization](#data-formats-and-serialization) | JSON, XML, form-data, multipart, Protocol Buffers |  High Priority |
| **API DESIGN & ARCHITECTURE** | | | |
| 6 | [RESTful API Design](#restful-api-design) | REST principles, resource naming, URL structure, idempotency |  Critical |
| 7 | [API Design Best Practices](#api-design-best-practices) | Consistency, naming conventions, resource relationships |  High Priority |
| 8 | [Request and Response Structure](#request-and-response-structure) | Headers, body, query parameters, path parameters |  Critical |
| 9 | [Error Handling & Status Codes](#error-handling--status-codes) | HTTP status codes, error response formats, error consistency |  Critical |
| 10 | [API Versioning Strategies](#api-versioning-strategies) | URI versioning, header versioning, semantic versioning |  High Priority |
| 11 | [Pagination, Filtering & Sorting](#pagination-filtering--sorting) | Handling large datasets, query parameters, cursor vs offset |  High Priority |
| **SECURITY & AUTHENTICATION** | | | |
| 12 | [API Authentication Methods](#api-authentication-methods) | API keys, Basic Auth, Bearer tokens, session-based auth |  Critical |
| 13 | [JWT (JSON Web Tokens)](#jwt-json-web-tokens) | Structure, claims, signing, refresh tokens, best practices |  High Priority |
| 14 | [OAuth 2.0 & OpenID Connect](#oauth-and-openid) | Authorization flows, scopes, third-party integration |  High Priority |
| 15 | [API Security Best Practices](#api-security-best-practices) | HTTPS, CORS, input validation, SQL injection, XSS prevention |  Critical |
| 16 | [Rate Limiting & Throttling](#rate-limiting-and-throttling) | Preventing abuse, quotas, sliding windows, Redis implementation |  High Priority |
| **DEVELOPMENT & IMPLEMENTATION** | | | |
| 17 | [Building REST APIs](#building-rest-apis) | Framework-specific implementation (Node.js, Laravel, Django, etc.) |  Critical |
| 18 | [API Validation](#api-validation) | Input validation, schema validation, request validation |  Critical |
| 19 | [Database Integration](#database-integration) | ORM usage, query optimization, N+1 problems, transactions |  High Priority |
| 20 | [File Upload APIs](#file-upload-apis) | Multipart forms, base64 encoding, cloud storage integration |  High Priority |
| 21 | [Middleware & Interceptors](#middleware--interceptors) | Authentication middleware, logging, request transformation |  High Priority |
| **ADVANCED API CONCEPTS** | | | |
| 22 | [GraphQL Fundamentals](#graphql-fundamentals) | Queries, mutations, subscriptions, schema design |  Advanced |
| 23 | [WebSockets & Real-time APIs](#websockets-and-real-time-apis) | Real-time communication, Socket.io, Server-Sent Events |  Advanced |
| 24 | [Webhooks](#webhooks) | Event-driven callbacks, webhook security, retry mechanisms |  High Priority |
| 25 | [API Gateway Patterns](#api-gateway-patterns) | Microservices, load balancing, service discovery |  Advanced |
| 26 | [Microservices Communication](#microservices-communication) | Service-to-service APIs, circuit breakers, timeouts |  Advanced |
| **PERFORMANCE & OPTIMIZATION** | | | |
| 27 | [Caching Strategies](#caching-strategies) | HTTP caching, ETags, Redis, CDN integration |  High Priority |
| 28 | [API Performance Optimization](#api-performance-optimization) | Query optimization, lazy loading, compression, CDN |  High Priority |
| 29 | [Database Optimization for APIs](#database-optimization-for-apis) | Indexing, connection pooling, read replicas |  Advanced |
| **TESTING & QUALITY** | | | |
| 30 | [API Testing Fundamentals](#api-testing-fundamentals) | Manual testing, automated testing, test types |  Critical |
| 31 | [Testing Tools & Techniques](#testing-tools--techniques) | Postman, Insomnia, curl, automated test frameworks ( Learn how to use Postman to test APIs (manual & automation basics)) |  Critical |
| 32 | [Unit & Integration Testing](#unit-and-integration-testing) | Test-driven development, mocking, test databases |  High Priority |
| 33 | [Load Testing & Performance Testing](#load-testing-and-performance-testing) | Stress testing, bottleneck identification |  Advanced |
| **DOCUMENTATION & STANDARDS** | | | |
| 34 | [API Documentation](#api-documentation) | OpenAPI/Swagger, Postman docs, interactive documentation (Learn how to generate documentation with Postman collections.) |  High Priority |
| 35 | [API Standards & Conventions](#api-standards-and-conventions) | JSON:API, HAL, OpenAPI specification |  High Priority |
| **CLIENT-SIDE INTEGRATION** | | | |
| 36 | [Consuming APIs - Frontend](#consuming-apis-frontend) | Fetch API, Axios, error handling, loading states |  Critical |
| 37 | [API Integration Patterns](#api-integration-patterns) | Retry logic, exponential backoff, circuit breakers |  High Priority |
| 38 | [Mobile API Integration](#mobile-api-integration) | Platform-specific considerations, offline support, sync |  High Priority |
| 39 | [State Management with APIs](#state-management-with-apis) | Redux, Context API, data fetching libraries (SWR, React Query) |  High Priority |
| **MONITORING & MAINTENANCE** | | | |
| 40 | [API Monitoring & Logging](#api-monitoring-and-logging) | Request logging, error tracking, performance mLearn how to generate documentation with Postman collections.etrics |  High Priority |
| 41 | [API Analytics & Metrics](#api-analytics--metrics) | Usage analytics, performance monitoring, business metrics |  Advanced |
| 42 | [Debugging APIs](#debugging-apis) | Common issues, debugging tools, troubleshooting techniques |  High Priority |
| **DEPLOYMENT & OPERATIONS** | | | |
| 43 | [API Deployment Strategies](#api-deployment-strategies) | Blue-green deployment, canary releases, rollback strategies |  Advanced |
| 44 | [CI/CD for APIs](#ci-cd-for-apis) | Automated testing, deployment pipelines, environment management |  High Priority |
| 45 | [API Version Management](#api-version-management) | Backward compatibility, deprecation strategies, migration |  Advanced |
| **THIRD-PARTY & EXTERNAL APIS** | | | |
| 46 | [Working with Third-Party APIs](#working-with-third-party-apis) | API keys management, rate limits, SDK usage |  Critical |
| 47 | [API Aggregation & Orchestration](#api-aggregation-and-orchestration) | Combining multiple APIs, data transformation |  Advanced |
| **PRACTICAL APPLICATION** | | | |
| 48 | [Real-World API Examples](#real-world-api-examples) | Complete request/response samples, common patterns |  Critical |
| 49 | [API Design Case Studies](#api-design-case-studies) | Analysis of popular APIs (Twitter, GitHub, Stripe) |  Advanced |
| 50 | [Building Your First API Project](#building-your-first-api-project) | End-to-end API development walkthrough |  Critical |




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### API Basics

🔹 Concept
- **API (Application Programming Interface)**: A set of rules and protocols for building and interacting with software applications.
- **Purpose**: Enables communication between different software systems (e.g., frontend ↔ backend, app ↔ server).
- **Key Benefits**:
	- Decouples client and server logic
	- Enables integration with third-party services
	- Promotes code reuse and modularity
- **Common Use Cases**:
	- Web APIs (REST, GraphQL)
	- Mobile app backends
	- Microservices communication
	- External integrations (payment, social login)

💻 Example
```http
GET /api/users HTTP/1.1
Host: example.com
Accept: application/json
```
Response:
```json
{
	"users": [
		{"id": 1, "name": "Ayush"},
		{"id": 2, "name": "Sam"}
	]
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Types of APIs

🔹 Concept
- **REST (Representational State Transfer)**:
	- Most common for web/mobile
	- Uses HTTP methods, stateless, resource-based URLs
- **SOAP (Simple Object Access Protocol)**:
	- XML-based, strict standards, used in enterprise
- **GraphQL**:
	- Query language for APIs, flexible data fetching
- **WebSockets**:
	- Real-time, bi-directional communication (chat, live updates)
- **RPC (Remote Procedure Call)**:
	- Directly calls functions/methods on remote server
- **gRPC**:
	- High-performance, uses Protocol Buffers, ideal for microservices

💡 When to use:
- REST: CRUD, public APIs, most web/mobile apps
- GraphQL: Flexible queries, reduce over-fetching
- WebSockets: Real-time apps (chat, notifications)
- SOAP: Legacy, strict contracts




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### HTTP Protocol Deep Dive

🔹 Concept
- **HTTP (HyperText Transfer Protocol)**: Foundation of data exchange on the web.
- **Request/Response Cycle**:
	- Client sends request → Server processes → Server sends response
- **Request Structure**:
	- Method (GET, POST, etc.)
	- URL/Endpoint
	- Headers (metadata: Content-Type, Authorization)
	- Body (data payload, for POST/PUT)
- **Response Structure**:
	- Status code (200 OK, 404 Not Found, 500 Server Error)
	- Headers (Content-Type, Set-Cookie)
	- Body (data, error message)
- **Content Negotiation**:
	- Client can request specific formats (JSON, XML) via Accept header
- **Common Headers**:
	- `Content-Type`: Format of request/response body
	- `Authorization`: Credentials/token
	- `Accept`: Desired response format

💻 Example
```http
POST /api/login HTTP/1.1
Host: example.com
Content-Type: application/json

{
	"email": "test@test.com",
	"password": "secret"
}
```
Response:
```json
{
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6..."
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### HTTP Methods

🔹 Concept
- **GET**: Retrieve data (safe, idempotent)
- **POST**: Create new resource (not idempotent)
- **PUT**: Update/replace resource (idempotent)
- **PATCH**: Partially update resource (idempotent)
- **DELETE**: Remove resource (idempotent)
- **OPTIONS**: Discover allowed methods
- **HEAD**: Like GET, but no response body

🔹 When to use:
- GET: Fetch user list, get product details
- POST: Register user, create order
- PUT: Update user profile (replace entire resource)
- PATCH: Update only email or password
- DELETE: Remove user, delete post

💻 Example
```http
GET /api/products/1
POST /api/products
PUT /api/products/1
PATCH /api/products/1
DELETE /api/products/1
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Data Formats and Serialization

🔹 Concept
- **Data Formats**: Defines how data is structured and exchanged between client and server.
	- **JSON (JavaScript Object Notation)**: Most common, lightweight, human-readable.
	- **XML (eXtensible Markup Language)**: Used in legacy and enterprise APIs.
	- **form-data / multipart**: For file uploads and complex forms.
	- **Protocol Buffers**: Binary format, used in gRPC for efficiency.
- **Serialization**: Converting data structures/objects into a format for transmission (e.g., object → JSON string).
- **Deserialization**: Converting received data back into usable objects.

💻 Example (JSON serialization in JavaScript):
```js
const user = { id: 1, name: "Ayush" };
const json = JSON.stringify(user); // Serialize
// json = '{"id":1,"name":"Ayush"}'
const obj = JSON.parse(json); // Deserialize
```

💡 In APIs: Always specify `Content-Type` header (e.g., `application/json`).




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### RESTful API Design

🔹 Concept
- **REST (Representational State Transfer)**: Architectural style for designing networked applications.
- **Principles**:
	- **Stateless**: Each request contains all info needed; server does not store client state.
	- **Resource-based**: Everything is a resource (user, product, order).
	- **Uniform Interface**: Consistent, predictable endpoints and methods.
	- **HTTP Methods**: Use GET, POST, PUT, PATCH, DELETE appropriately.
	- **Idempotency**: Safe to repeat certain requests (GET, PUT, DELETE).
- **Resource Naming**:
	- Use plural nouns: `/api/users`, `/api/products`
	- Use nested resources for relationships: `/api/users/1/orders`
- **URL Structure**:
	- `/api/resource/:id` for single item
	- `/api/resource` for collection

💻 Example
```http
GET /api/users/1
POST /api/users
PUT /api/users/1
DELETE /api/users/1
```
Response (JSON):
```json
{
	"id": 1,
	"name": "Ayush"
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Design Best Practices

🔹 Concept
- **Consistency**: Use consistent naming, structure, and response formats.
- **Versioning**: Add version to API (e.g., `/api/v1/users`) to avoid breaking changes.
- **Error Handling**: Return clear, structured error messages with status codes.
- **Documentation**: Use OpenAPI/Swagger, Postman, or markdown for API docs.
- **Security**: Always use HTTPS, validate input, and protect sensitive endpoints.
- **Pagination, Filtering, Sorting**: For large datasets, support query params like `?page=2&limit=10`.
- **Status Codes**: Use standard HTTP codes (200 OK, 201 Created, 400 Bad Request, 404 Not Found, 500 Server Error).
- **Avoid Over-fetching/Under-fetching**: Return only necessary data.

💻 Example (Error response):
```json
{
	"error": {
		"code": 404,
		"message": "User not found"
	}
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Request and Response Structure

🔹 Concept
- **Request Structure**:
	- **Endpoint/URL**: `/api/users/1`
	- **Method**: GET, POST, etc.
	- **Headers**: Metadata (Content-Type, Authorization)
	- **Body**: Data payload (for POST/PUT/PATCH)
- **Response Structure**:
	- **Status Code**: Indicates result (200, 404, 500)
	- **Headers**: Content-Type, Set-Cookie, etc.
	- **Body**: Data or error message
- **Query Parameters**: For filtering, pagination, etc. (e.g., `/api/users?page=2`)
- **Path Parameters**: For resource IDs (e.g., `/api/users/1`)

💻 Example (Request):
```http
POST /api/users HTTP/1.1
Host: example.com
Content-Type: application/json

{
	"name": "Ayush",
	"email": "ayush@example.com"
}
```
Response:
```json
{
	"id": 1,
	"name": "Ayush",
	"email": "ayush@example.com"
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Error Handling & Status Codes

🔹 Concept
- **Error Handling**: APIs should return clear, consistent error responses with appropriate status codes.
- **Status Codes**:
	- 200 OK: Success
	- 201 Created: Resource created
	- 400 Bad Request: Invalid input
	- 401 Unauthorized: Authentication required
	- 403 Forbidden: No permission
	- 404 Not Found: Resource missing
	- 500 Internal Server Error: Server issue
- **Error Response Format**:
	- Use structured JSON for errors
	- Include code, message, and (optionally) details

💻 Example (Error response):
```json
{
	"error": {
		"code": 400,
		"message": "Invalid request data",
		"details": ["Email is required", "Password too short"]
	}
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Versioning Strategies

🔹 Concept
- **Versioning**: Prevents breaking changes for clients when APIs evolve.
- **Common Strategies**:
	- **URI Versioning**: `/api/v1/users`
	- **Header Versioning**: `Accept: application/vnd.example.v1+json`
	- **Query Parameter**: `/api/users?version=1`
- **Best Practices**:
	- Use semantic versioning (v1, v2, etc.)
	- Document deprecated endpoints
	- Communicate breaking changes early

💻 Example (URI versioning):
```http
GET /api/v1/products
GET /api/v2/products
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Pagination, Filtering & Sorting

🔹 Concept
- **Pagination**: Splits large datasets into pages for efficient loading.
	- Use query params: `?page=2&limit=10`
- **Filtering**: Allows clients to narrow results (e.g., `?status=active`)
- **Sorting**: Orders results by field (e.g., `?sort=name&order=asc`)
- **Best Practices**:
	- Return metadata (total count, current page)
	- Support cursor-based pagination for large/real-time datasets

💻 Example (Paginated response):
```json
{
	"data": [ ... ],
	"meta": {
		"total": 100,
		"page": 2,
		"limit": 10
	}
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Authentication Methods

🔹 Concept
- **Authentication**: Verifies user/client identity before granting access.
- **Common Methods**:
	- **API Keys**: Simple, static tokens in header or query param
	- **Basic Auth**: Username/password in header (not recommended for public APIs)
	- **Bearer Tokens**: JWT or OAuth tokens in `Authorization: Bearer <token>`
	- **Session-based**: Cookie/session for web apps
- **Best Practices**:
	- Always use HTTPS
	- Store secrets securely
	- Expire/revoke tokens as needed

💻 Example (Bearer token):
```http
GET /api/profile
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### JWT JSON Web Tokens

🔹 Concept
- **JWT**: A compact, URL-safe token format for securely transmitting information between parties.
- **Structure**: Three parts separated by dots: `header.payload.signature`
	- **Header**: Algorithm & token type
	- **Payload**: Claims (user info, permissions, expiry)
	- **Signature**: Verifies integrity (signed with secret or private key)
- **Common Claims**: `sub` (subject/user), `exp` (expiry), `iat` (issued at), `role`, etc.
- **Best Practices**:
	- Always validate signature and expiry
	- Never store sensitive info in payload
	- Use HTTPS for transmission

💻 Example (JWT payload):
```json
{
	"sub": "1234567890",
	"name": "Ayush",
	"role": "admin",
	"exp": 1710000000
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### OAuth 2.0 & OpenID Connect

🔹 Concept
- **OAuth 2.0**: Authorization framework for delegated access ("Login with Google/Facebook").
- **OpenID Connect**: Layer on top of OAuth for authentication (user identity).
- **Flows**:
	- **Authorization Code**: Most secure, used by web/mobile apps
	- **Implicit**: For single-page apps (less secure)
	- **Client Credentials**: For server-to-server
- **Scopes**: Define what access is granted (e.g., `profile`, `email`)
- **Tokens**: Access token (short-lived), refresh token (get new access token)
- **Best Practices**:
	- Use HTTPS
	- Validate tokens and scopes
	- Store client secrets securely

💻 Example (OAuth flow):
```http
GET /authorize?client_id=abc&redirect_uri=https://app.com/callback&scope=profile&response_type=code
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Security Best Practices

🔹 Concept
- **HTTPS**: Always use SSL/TLS for encrypted communication
- **CORS (Cross-Origin Resource Sharing)**: Restrict which domains can access your API
- **Input Validation**: Sanitize and validate all incoming data
- **SQL Injection Prevention**: Use prepared statements/ORM
- **XSS Prevention**: Escape output, validate input
- **Authentication & Authorization**: Use strong methods (JWT, OAuth, API keys)
- **Rate Limiting**: Prevent brute force and abuse
- **Logging & Monitoring**: Track suspicious activity
- **Least Privilege Principle**: Grant only necessary permissions

💻 Example (CORS header):
```http
Access-Control-Allow-Origin: https://yourapp.com
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Rate Limiting and Throttling

🔹 Concept
- **Rate Limiting**: Restricts number of requests per user/IP in a time window
- **Throttling**: Slows down requests after a threshold
- **Techniques**:
	- Fixed window: e.g., 100 requests per minute
	- Sliding window: More accurate, tracks recent requests
	- Token bucket/leaky bucket: Flexible algorithms
- **Implementation**:
	- Use Redis or in-memory store for counters
	- Return `429 Too Many Requests` when limit exceeded
- **Best Practices**:
	- Inform clients of limits via headers
	- Allow burst traffic but control sustained load

💻 Example (Rate limit headers):
```http
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 10
X-RateLimit-Reset: 1710000000
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Building REST APIs

🔹 Concept
- **REST API Implementation**: Building endpoints that follow REST principles using frameworks (Node.js/Express, Laravel, Django, etc.)
- **Routing**: Map HTTP methods and URLs to controller functions.
- **Controllers**: Handle business logic and interact with models/services.
- **Models/ORM**: Represent and manage data (e.g., Eloquent in Laravel, Sequelize in Node.js).
- **Middleware**: Add authentication, logging, validation, etc.
- **Response Formatting**: Return consistent JSON responses.

💻 Example (Express.js):
```js
app.get('/api/users', (req, res) => {
	res.json([{ id: 1, name: 'Ayush' }]);
});
```
💻 Example (Laravel):
```php
Route::get('/api/users', [UserController::class, 'index']);
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Validation

🔹 Concept
- **Input Validation**: Ensure incoming data is correct and safe.
- **Schema Validation**: Define expected structure (e.g., JSON Schema, Laravel Form Requests).
- **Request Validation**: Validate query params, body, headers.
- **Error Handling**: Return clear error messages for invalid data.
- **Best Practices**:
	- Validate on both client and server
	- Use libraries/framework features for validation

💻 Example (Laravel):
```php
$request->validate([
	'email' => 'required|email',
	'password' => 'required|min:8',
]);
```
💻 Example (Express.js with Joi):
```js
const schema = Joi.object({ email: Joi.string().email().required() });
const { error } = schema.validate(req.body);
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Database Integration

🔹 Concept
- **ORM (Object-Relational Mapping)**: Maps database tables to objects (Eloquent, Sequelize, Django ORM).
- **Query Optimization**: Use indexes, avoid N+1 queries, optimize joins.
- **Transactions**: Ensure data consistency for multi-step operations.
- **Relationships**: Model one-to-many, many-to-many, etc.
- **Best Practices**:
	- Use eager loading to avoid N+1
	- Handle errors and rollbacks in transactions

💻 Example (Laravel Eloquent):
```php
$users = User::with('posts')->get(); // Eager loading
DB::transaction(function () {
	// ...multiple DB operations
});
```
💻 Example (Node.js Sequelize):
```js
User.findAll({ include: Post });
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### File Upload APIs

🔹 Concept
- **File Uploads**: Allow clients to send files (images, docs) via API.
- **Multipart Forms**: Use `multipart/form-data` for file uploads.
- **Base64 Encoding**: Alternative for small files, but less efficient.
- **Cloud Storage Integration**: Store files in S3, Google Cloud, etc.
- **Validation**: Check file type, size, and scan for malware.
- **Best Practices**:
	- Limit file size and type
	- Store files securely (outside public web root)
	- Return file URLs or IDs in response

💻 Example (Express.js with Multer):
```js
app.post('/upload', upload.single('file'), (req, res) => {
	res.json({ url: `/uploads/${req.file.filename}` });
});
```
💻 Example (Laravel):
```php
if ($request->hasFile('avatar')) {
	$path = $request->file('avatar')->store('avatars');
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Middleware and Interceptors

🔹 Concept
- **Middleware**: Functions that process requests before they reach your main handler/controller (authentication, logging, validation).
- **Interceptors**: Similar to middleware, but often used to transform requests/responses (common in frameworks like NestJS, Spring).
- **Use Cases**:
	- Authentication & authorization
	- Logging requests/responses
	- Input validation/sanitization
	- Request/response transformation
- **Best Practices**:
	- Keep middleware modular and reusable
	- Order matters: authentication before logging, etc.
	- Handle errors gracefully

💻 Example (Express.js Middleware):
```js
function authMiddleware(req, res, next) {
	if (!req.headers.authorization) {
		return res.status(401).json({ error: 'Unauthorized' });
	}
	next();
}
app.use(authMiddleware);
```
💻 Example (NestJS Interceptor):
```ts
@Injectable()
export class LoggingInterceptor implements NestInterceptor {
	intercept(context, next) {
		console.log('Request...');
		return next.handle();
	}
}

💻 Example (Laravel Middleware):
```php
// app/Http/Middleware/Authenticate.php
public function handle($request, Closure $next)
{
	if (!auth()->check()) {
		return response()->json(['error' => 'Unauthorized'], 401);
	}
	return $next($request);
}
// Register in app/Http/Kernel.php
protected $routeMiddleware = [
	'auth' => \App\Http\Middleware\Authenticate::class,
];
// Usage in routes/web.php
Route::get('/dashboard', 'DashboardController@index')->middleware('auth');
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### GraphQL Fundamentals

🔹 Concept
- **GraphQL**: Query language for APIs, allows clients to request exactly the data they need.
- **Schema**: Defines types, queries, mutations, and subscriptions.
- **Queries**: Fetch data
- **Mutations**: Modify data
- **Subscriptions**: Real-time updates
- **Benefits**:
	- Reduces over-fetching/under-fetching
	- Strongly typed schema
	- Single endpoint for all operations
- **Best Practices**:
	- Design clear, intuitive schema
	- Use resolvers for business logic
	- Secure queries and mutations

💻 Example (GraphQL Query):
```graphql
query {
	user(id: 1) {
		id
		name
		posts {
			title
		}
	}
}
```

💻 Example (Schema Definition):
```graphql
type User {
	id: ID!
	name: String!
	posts: [Post]
}
type Query {
	user(id: ID!): User
}
```

💻 Example (Laravel Lighthouse GraphQL):
```graphql
# schema.graphql
type User {
	id: ID!
	name: String!
	posts: [Post!]! @hasMany
}
type Query {
	user(id: ID!): User @find
}
```

```php
// app/Models/User.php (Eloquent Model)
class User extends Model {
		public function posts() {
				return $this->hasMany(Post::class);
		}
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### WebSockets and Real-time APIs

🔹 Concept
- **WebSockets**: Protocol for real-time, bi-directional communication between client and server.
- **Real-time APIs**: Enable instant updates (chat, notifications, live dashboards).
- **Server-Sent Events (SSE)**: One-way real-time updates from server to client.
- **Socket.io**: Popular library for WebSockets in Node.js.
- **Use Cases**:
	- Chat applications
	- Live notifications
	- Collaborative editing
- **Best Practices**:
	- Authenticate connections
	- Handle disconnects/retries
	- Limit broadcast scope (rooms/channels)

💻 Example (Node.js with Socket.io):
```js
const io = require('socket.io')(server);
io.on('connection', (socket) => {
	socket.emit('welcome', 'Hello!');
	socket.on('message', (msg) => {
		io.emit('message', msg);
	});
});
```

💻 Example (SSE):
```js
app.get('/events', (req, res) => {
	res.setHeader('Content-Type', 'text/event-stream');
	res.write('data: Hello\n\n');
});
```

💻 Example (Laravel WebSockets with beyondcode/laravel-websockets):
```php
// Broadcasting an event
event(new MessageSent($user, $message));

// app/Events/MessageSent.php
class MessageSent implements ShouldBroadcast {
	public $user, $message;
	public function __construct($user, $message) {
		$this->user = $user;
		$this->message = $message;
	}
	public function broadcastOn() {
		return ['chat-channel'];
	}
}
```

Frontend listens via Laravel Echo:

```js
Echo.channel('chat-channel')
	.listen('MessageSent', (e) => {
		console.log(e.user, e.message);
	});
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Webhooks

🔹 Concept
- **Webhooks**: HTTP callbacks triggered by events (e.g., payment received, repo push).
- **Event-driven**: Server notifies client when something happens.
- **Security**:
	- Validate incoming requests (signatures, secrets)
	- Use HTTPS
- **Retry Mechanisms**: Handle failed deliveries with retries/backoff.
- **Best Practices**:
	- Document webhook payloads and events
	- Log deliveries and failures
	- Respond quickly (acknowledge receipt)

💻 Example (Webhook Handler in Express.js):
```js
app.post('/webhook', (req, res) => {
	// Validate signature
	// Process event
	res.status(200).send('Received');
});
```

💻 Example (Webhook Payload):
```json
{
	"event": "payment_success",
	"data": {
		"user_id": 1,
		"amount": 100
	}
}
```

💻 Example (Laravel Webhook Handler):

```php
// routes/web.php
Route::post('/webhook', 'WebhookController@handle');

// app/Http/Controllers/WebhookController.php
public function handle(Request $request)
{
	// Validate signature
	if ($request->header('X-Signature') !== env('WEBHOOK_SECRET')) {
		return response()->json(['error' => 'Invalid signature'], 403);
	}
	// Process event
	\Log::info('Webhook received', $request->all());
	return response('Received', 200);
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Gateway Patterns

🔹 Concept
- **API Gateway**: Central entry point for client requests in microservices architecture.
- **Responsibilities**:
	- Request routing to appropriate microservice
	- Load balancing
	- Authentication & authorization
	- Rate limiting & throttling
	- Aggregating responses from multiple services
	- Service discovery
- **Popular Tools**: Kong, NGINX, AWS API Gateway, Zuul, Traefik
- **Best Practices**:
	- Use gateway for cross-cutting concerns (auth, logging)
	- Keep business logic in microservices, not gateway
	- Secure gateway endpoints

💻 Example (NGINX API Gateway config):
```nginx
location /api/ {
	proxy_pass http://microservice_cluster;
	proxy_set_header Authorization $http_authorization;
}
```
💻 Example (Laravel with AWS API Gateway):
```php
// API Gateway routes traffic to Laravel Lambda function
Route::get('/products', 'ProductController@index');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Microservices Communication

🔹 Concept
- **Microservices**: Independent services communicating over APIs (HTTP, gRPC, message queues).
- **Patterns**:
	- Synchronous (REST, gRPC)
	- Asynchronous (RabbitMQ, Kafka, SQS)
- **Challenges**:
	- Service discovery
	- Circuit breakers (prevent cascading failures)
	- Timeouts & retries
	- Data consistency
- **Best Practices**:
	- Use API Gateway for routing
	- Implement circuit breakers (e.g., Hystrix, Laravel Rescue)
	- Set reasonable timeouts
	- Use idempotency for safe retries

💻 Example (Node.js with Axios & Circuit Breaker):
```js
const axios = require('axios');
const { breaker } = require('opossum');
const getUser = breaker(() => axios.get('http://user-service/api/users/1'));
getUser.fire().then(console.log).catch(console.error);
```
💻 Example (Laravel Service Communication):
```php
// Synchronous HTTP call
$response = Http::get('http://user-service/api/users/1');
// Asynchronous with queue
dispatch(new SyncUserJob($userId));
// Circuit breaker (custom)
try {
		$response = Http::timeout(2)->get('http://user-service/api/users/1');
} catch (Exception $e) {
		// Fallback logic
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Caching Strategies

🔹 Concept
- **Caching**: Store frequently accessed data to reduce load and improve speed.
- **Types**:
	- HTTP caching (browser, CDN)
	- Server-side caching (Redis, Memcached)
	- Object caching (Eloquent, ORM)
- **Techniques**:
	- ETags for cache validation
	- Cache-Control headers
	- In-memory cache for fast access
- **Best Practices**:
	- Set appropriate cache expiry
	- Invalidate cache on data change
	- Use CDN for static assets

💻 Example (HTTP Cache-Control header):
```http
Cache-Control: public, max-age=3600
ETag: "abc123"
```
💻 Example (Laravel Redis Cache):
```php
// Store in cache
Cache::put('user_1', $user, 600);
// Retrieve from cache
$user = Cache::get('user_1');
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Performance Optimization

🔹 Concept
- **Performance Optimization**: Techniques to make APIs faster and more efficient.
- **Strategies**:
	- Query optimization (indexes, joins)
	- Lazy loading vs eager loading
	- Response compression (gzip)
	- CDN for static assets
	- Reduce payload size (fields, pagination)
- **Best Practices**:
	- Profile and monitor API performance
	- Optimize database queries
	- Use pagination for large datasets
	- Compress responses

💻 Example (Express.js Gzip Compression):
```js
const compression = require('compression');
app.use(compression());
```
💻 Example (Laravel Performance):
```php
// Eager loading to reduce queries
$users = User::with('posts')->get();
// Pagination
$users = User::paginate(20);
// Response compression (handled by web server or middleware)
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Database Optimization for APIs

🔹 Concept
- **Database Optimization**: Techniques to improve API speed, scalability, and reliability.
- **Key Strategies**:
	- Indexing: Speed up queries by creating indexes on frequently searched columns.
	- Connection Pooling: Reuse database connections for efficiency.
	- Read Replicas: Distribute read queries to replica databases for scalability.
	- Query Optimization: Avoid N+1 queries, use joins wisely, limit result sets.
	- Caching: Store frequent query results in cache (Redis, Memcached).
- **Best Practices**:
	- Monitor slow queries and optimize them
	- Use pagination for large datasets
	- Regularly review and add indexes
	- Separate read/write workloads

💻 Example (Laravel Index Migration):
```php
Schema::table('users', function (Blueprint $table) {
		$table->index('email');
});
```
💻 Example (Laravel Connection Pooling):
```php
// Managed by Laravel and database driver (e.g., MySQL, PostgreSQL)
// Configure pool size in database config
```
💻 Example (Laravel Read Replica):
```php
// config/database.php
'read' => [
		'host' => ['replica1', 'replica2'],
],
'write' => [
		'host' => ['master'],
],
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Testing Fundamentals

🔹 Concept
- **API Testing**: Ensures APIs work as expected and meet requirements.
- **Types**:
	- Manual Testing: Using tools like Postman, curl
	- Automated Testing: Scripts and frameworks (PHPUnit, Jest, Mocha)
	- Functional Testing: Validate endpoints and business logic
	- Integration Testing: Test API with database, services
	- Load/Performance Testing: Assess scalability and speed
- **Best Practices**:
	- Test all endpoints, including error cases
	- Use mock data for repeatable tests
	- Automate regression tests

💻 Example (Laravel Feature Test):
```php
public function testUserApiReturnsData()
{
		$response = $this->getJson('/api/users');
		$response->assertStatus(200)
						 ->assertJsonStructure([
								 '*' => ['id', 'name', 'email']
						 ]);
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Testing Tools and Techniques

🔹 Concept
- **API Testing Tools**: Help automate and simplify API testing.
- **Popular Tools**:
	- Postman: Manual/automated API tests, collections, environments
	- Insomnia: Similar to Postman, great for REST/GraphQL
	- curl: Command-line HTTP requests
	- PHPUnit: Automated tests for PHP/Laravel
	- Jest/Mocha: Automated tests for Node.js
- **Techniques**:
	- Use environments for different configs (dev, prod)
	- Automate tests in CI/CD pipelines
	- Use mock servers for isolated testing
- **Best Practices**:
	- Document test cases and expected results
	- Test authentication, error handling, edge cases

💻 Example (Postman Test Script):
```js
pm.test('Status code is 200', function () {
	pm.response.to.have.status(200);
});
```
💻 Example (Laravel PHPUnit Test):
```php
public function testCreateUser()
{
		$response = $this->postJson('/api/users', [
				'name' => 'Ayush',
				'email' => 'ayush@example.com',
				'password' => 'secret',
		]);
		$response->assertStatus(201)
						 ->assertJson(['name' => 'Ayush']);
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Unit and Integration Testing

🔹 Concept
- **Unit Testing**: Test individual functions/components in isolation.
- **Integration Testing**: Test how components/services work together (API + DB).
- **Test-driven Development (TDD)**: Write tests before code for reliability.
- **Mocking**: Simulate dependencies (DB, services) for isolated tests.
- **Test Databases**: Use separate DB for tests to avoid data pollution.
- **Best Practices**:
  - Write tests for all critical logic
  - Use factories/fake data for test setup
  - Clean up test data after each run
  - Automate tests in CI/CD

💻 Example (Laravel Unit Test):
```php
public function testAddNumbers()
{
	$result = add(2, 3);
	$this->assertEquals(5, $result);
}
```
💻 Example (Laravel Integration Test):
```php
public function testUserCreationStoresInDatabase()
{
	$response = $this->postJson('/api/users', [
		'name' => 'Sam',
		'email' => 'sam@example.com',
		'password' => 'secret',
	]);
	$response->assertStatus(201);
	$this->assertDatabaseHas('users', ['email' => 'sam@example.com']);
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Load Testing and Performance Testing

🔹 Concept
- **Load Testing**: Simulate high traffic to measure API scalability and reliability.
- **Performance Testing**: Identify bottlenecks and optimize response times.
- **Tools**:
	- Apache JMeter, k6, Artillery, Locust
	- Laravel: Use `php artisan test --parallel` for concurrent tests
- **Metrics**:
	- Response time, throughput, error rate, resource usage
- **Best Practices**:
	- Test with realistic data and scenarios
	- Monitor server/database during tests
	- Automate load tests in CI/CD

💻 Example (Artillery YAML):
```yaml
config:
	target: "https://api.example.com"
	phases:
		- duration: 60
			arrivalRate: 10
scenarios:
	- flow:
			- get:
					url: "/users"
```
💻 Example (Laravel Parallel Test):
```sh
php artisan test --parallel
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Documentation

🔹 Concept
- **API Documentation**: Describes endpoints, request/response formats, authentication, errors, etc.
- **Tools**:
	- OpenAPI/Swagger: Interactive docs, auto-generated from code
	- Postman: Collections, examples, environment variables
	- Laravel: Use `knuckleswtf/scribe` for auto-generated docs
- **Best Practices**:
	- Keep docs up-to-date with code
	- Include sample requests/responses
	- Document authentication, error formats, rate limits

💻 Example (OpenAPI YAML):
```yaml
paths:
	/users:
		get:
			summary: Get all users
			responses:
				'200':
					description: Success
					content:
						application/json:
							schema:
								type: array
								items:
									$ref: '#/components/schemas/User'
```
💻 Example (Laravel Scribe):
```php
/**
 * Get all users
 * @response 200 {"id":1,"name":"Ayush"}
 */
public function index() {
		return User::all();
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->
### API Standards and Conventions

🔹 Concept
- **API Standards**: Ensure consistency, interoperability, and predictability.
- **Popular Standards**:
	- JSON:API: Standard for JSON responses (links, meta, errors)
	- HAL (Hypertext Application Language): Embeds links in JSON/XML
	- OpenAPI Specification: Defines endpoints, schemas, security
- **Best Practices**:
	- Use consistent naming and structure
	- Follow standard error formats
	- Document conventions in API docs

💻 Example (JSON:API Response):
```json
{
	"data": {
		"type": "user",
		"id": "1",
		"attributes": {
			"name": "Ayush"
		}
	}
}
```
💻 Example (OpenAPI Path):
```yaml
paths:
	/users:
		get:
			summary: Get all users
			responses:
				'200':
					description: Success
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Consuming APIs Frontend

🔹 Concept
- **Consuming APIs**: Frontend apps fetch and display data from APIs.
- **Tools/Libraries**:
	- Fetch API (native JS)
	- Axios (promise-based HTTP client)
	- React Query, SWR (data fetching/state management)
- **Patterns**:
	- Error handling (try/catch, .catch)
	- Loading states (spinners, skeletons)
	- Data transformation (mapping, filtering)
- **Best Practices**:
	- Handle errors gracefully
	- Show loading indicators
	- Cache data for performance

💻 Example (Fetch API):
```js
fetch('/api/users')
	.then(res => res.json())
	.then(data => console.log(data))
	.catch(err => console.error(err));
```
💻 Example (Axios):
```js
import axios from 'axios';
const getUsers = async () => {
	try {
		const res = await axios.get('/api/users');
		console.log(res.data);
	} catch (err) {
		console.error(err);
	}
};
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Integration Patterns

🔹 Concept
- **API Integration Patterns**: Strategies for reliable, resilient API calls.
- **Patterns**:
	- Retry logic: Automatically retry failed requests
	- Exponential backoff: Increase wait time between retries
	- Circuit breakers: Prevent repeated failures from overwhelming system
- **Best Practices**:
	- Limit number of retries
	- Log failed attempts
	- Use idempotency for safe retries

💻 Example (Axios Retry Logic):
```js
import axios from 'axios';
import axiosRetry from 'axios-retry';
axiosRetry(axios, { retries: 3, retryDelay: axiosRetry.exponentialDelay });
axios.get('/api/data').catch(console.error);
```
💻 Example (Node.js Circuit Breaker):
```js
const { breaker } = require('opossum');
const apiCall = breaker(() => axios.get('/api/data'));
apiCall.fire().catch(console.error);
```
💻 Example (Laravel Retry Logic):
```php
// Retry HTTP request up to 3 times with 100ms delay
$response = retry(3, function () {
		return Http::get('https://api.example.com/data');
}, 100);
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Mobile API Integration

🔹 Concept
- **Mobile API Integration**: Connecting mobile apps to APIs with reliability and performance.
- **Considerations**:
	- Network variability (offline, slow, intermittent)
	- Data sync (local storage, background sync)
	- Authentication (OAuth, JWT)
	- Efficient data transfer (pagination, compression)
- **Best Practices**:
	- Cache data locally for offline use
	- Use background sync for updates
	- Handle errors and retries gracefully

💻 Example (React Native Fetch with Offline Support):
```js
import NetInfo from '@react-native-community/netinfo';
const fetchData = async () => {
	const isConnected = await NetInfo.fetch();
	if (isConnected) {
		// Fetch from API
		const res = await fetch('/api/data');
		// Save to local storage
	} else {
		// Load from local storage
	}
};
```
💻 Example (Laravel API for Mobile):
```php
// API endpoint returns paginated data for mobile
public function index(Request $request) {
		return User::paginate(20);
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### State Management with APIs

🔹 Concept
- **State Management**: Handling API data in frontend apps (React, Vue, etc.).
- **Libraries**:
	- Redux, Context API (React)
	- SWR, React Query (data fetching, caching)
- **Patterns**:
	- Centralized store for API data
	- Automatic refetching and cache updates
	- Optimistic UI updates
- **Best Practices**:
	- Normalize data for easy access
	- Use selectors for derived data
	- Handle loading/error states

💻 Example (React Query):
```js
import { useQuery } from 'react-query';
const { data, isLoading, error } = useQuery('users', () => fetch('/api/users').then(res => res.json()));
```
💻 Example (Laravel API for State Management):
```php
// API endpoint for frontend state management
public function getUsers() {
		return User::all();
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Monitoring and Logging

🔹 Concept
- **API Monitoring & Logging**: Track API usage, errors, and performance for reliability and debugging.
- **Techniques**:
	- Request/response logging
	- Error tracking (Sentry, Bugsnag)
	- Performance metrics (response time, throughput)
	- Health checks
- **Best Practices**:
	- Log all requests and errors
	- Monitor key metrics and set alerts
	- Use structured logs (JSON)

💻 Example (Express.js Logging Middleware):
```js
app.use((req, res, next) => {
	console.log(`${req.method} ${req.url}`);
	next();
});
```
💻 Example (Laravel Logging):
```php
// Log request and response in middleware
public function handle($request, Closure $next)
{
		\Log::info('Request', $request->all());
		$response = $next($request);
		\Log::info('Response', $response->getContent());
		return $response;
}
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Analytics and Metrics
🔹 Concept
- **API Analytics**: Track usage, performance, and business metrics to understand how APIs are used and improve reliability.
- **Metrics**:
	- Request count, error rate, latency, response time
	- User activity, endpoint popularity
	- Business KPIs (e.g., transactions, revenue)
- **Tools**:
	- Google Analytics (for frontend APIs)
	- Prometheus + Grafana (backend metrics)
	- Datadog, New Relic, AWS CloudWatch
- **Best Practices**:
	- Instrument endpoints for metrics collection
	- Monitor key metrics and set alerts
	- Use dashboards for visualization
	- Track custom business events

💻 Example (Node.js with Prometheus):
```js
const client = require('prom-client');
const httpRequestDurationMicroseconds = new client.Histogram({
	name: 'http_request_duration_ms',
	help: 'Duration of HTTP requests in ms',
	labelNames: ['method', 'route', 'code'],
});
app.use((req, res, next) => {
	const end = httpRequestDurationMicroseconds.startTimer();
	res.on('finish', () => {
		end({ method: req.method, route: req.route?.path, code: res.statusCode });
	});
	next();
});
```

💻 Example (Frontend API Analytics):
```js
// Track API call in Google Analytics
fetch('/api/data').then(() => {
	gtag('event', 'api_call', { event_category: 'API', event_label: '/api/data' });
});
```

💻 Example (Laravel Metrics with Telescope):
```php
// Install Laravel Telescope for request monitoring
// composer require laravel/telescope
// php artisan telescope:install && php artisan migrate
// Telescope automatically tracks requests, exceptions, jobs, DB queries, etc.
// View dashboard at /telescope
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Debugging APIs
🔹 Concept
- **Debugging APIs**: Identifying and resolving issues in API endpoints, logic, or integrations.
- **Common Issues**:
	- Incorrect request/response formats
	- Authentication/authorization failures
	- Database errors, timeouts
	- Network issues, CORS errors
- **Techniques**:
	- Use logging (request, error, stack trace)
	- Inspect requests/responses with tools (Postman, curl, browser dev tools)
	- Add debug endpoints or verbose error messages (in dev only)
	- Use breakpoints and step-through debugging (IDE)
- **Best Practices**:
	- Log all errors with context
	- Mask sensitive data in logs
	- Use correlation IDs for tracing requests
	- Document common troubleshooting steps

💻 Example (Express.js Error Logging):
```js
app.use((err, req, res, next) => {
	console.error('Error:', err.message, err.stack);
	res.status(500).json({ error: 'Internal Server Error' });
});
```

💻 Example (Debugging with Postman):
// Use Postman Console to inspect request/response, headers, and errors.

💻 Example (Laravel Debugging with Log & Telescope):
```php
// Log error in Laravel
try {
	// ...API logic
} catch (Exception $e) {
	\Log::error('API error', ['message' => $e->getMessage(), 'trace' => $e->getTraceAsString()]);
	return response()->json(['error' => 'Internal Server Error'], 500);
}
// Use Telescope for request/error inspection
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Deployment Strategies
🔹 Concept
- **Deployment Strategies**: Methods for releasing new API versions with minimal downtime and risk.
- **Common Strategies**:
	- Blue-Green Deployment: Two environments (blue/green); switch traffic after successful deploy.
	- Canary Releases: Gradually roll out new version to a subset of users.
	- Rolling Updates: Update servers one by one.
	- Feature Flags: Enable/disable features without redeploying.
- **Best Practices**:
	- Automate deployments (CI/CD)
	- Monitor health and rollback on failure
	- Use versioning for backward compatibility
	- Document deployment process

💻 Example (Blue-Green Deployment with NGINX):
```nginx
# Two upstreams: blue and green
upstream blue_backend { server 10.0.0.1; }
upstream green_backend { server 10.0.0.2; }
server {
	location /api/ {
		proxy_pass http://blue_backend; # Switch to green_backend after deploy
	}
}
```

💻 Example (Canary Release with Kubernetes):
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
	name: api-canary
spec:
	replicas: 1 # Small subset
	template:
		metadata:
			labels:
				version: canary
				app: api
				...
```

💻 Example (Laravel Zero-Downtime Deploy with Envoy):
```php
// Install Laravel Envoy
// composer require laravel/envoy
// Envoy.blade.php
@servers(['web' => 'user@your-server.com'])

@task('deploy', ['on' => 'web'])
	cd /var/www/app
	git pull origin main
	php artisan migrate --force
	php artisan config:cache
@endtask
// Run: envoy run deploy
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### CI CD for APIs
🔹 Concept
- **CI/CD (Continuous Integration/Continuous Deployment)**: Automate building, testing, and deploying APIs for faster, safer releases.
- **Key Steps**:
	- Code pushed to repository (GitHub, GitLab)
	- Automated tests run (unit, integration, lint)
	- Build artifacts (Docker image, zip, etc.)
	- Deploy to staging/production
- **Tools**:
	- GitHub Actions, GitLab CI, Jenkins, CircleCI
	- Docker, Kubernetes, AWS CodePipeline
- **Best Practices**:
	- Automate all steps (test, build, deploy)
	- Use environment variables for secrets
	- Run tests before deploy
	- Rollback on failure

💻 Example (GitHub Actions for Node.js API):
```yaml
name: CI/CD Pipeline
on:
	push:
		branches: [main]
jobs:
	build-and-deploy:
		runs-on: ubuntu-latest
		steps:
			- uses: actions/checkout@v2
			- name: Set up Node.js
				uses: actions/setup-node@v2
				with:
					node-version: '16'
			- run: npm install
			- run: npm test
			- run: npm run build
			- name: Deploy
				run: echo "Deploy step here"
```

💻 Example (Laravel CI/CD with GitHub Actions):
```yaml
name: Laravel CI/CD
on:
	push:
		branches: [main]
jobs:
	laravel-tests:
		runs-on: ubuntu-latest
		steps:
			- uses: actions/checkout@v2
			- name: Set up PHP
				uses: shivammathur/setup-php@v2
				with:
					php-version: '8.1'
			- run: composer install --prefer-dist --no-progress --no-suggest
			- run: cp .env.example .env
			- run: php artisan key:generate
			- run: php artisan migrate --force
			- run: php artisan test
			- name: Deploy
				run: echo "Deploy step here"
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Version Management

🔹 Concept
- **API Version Management**: Strategies to evolve APIs without breaking existing clients.
- **Backward Compatibility**: Ensure old clients continue to work with new API versions.
- **Deprecation Strategies**:
	- Announce deprecated endpoints in advance
	- Provide migration guides
	- Use response headers to warn about deprecation
- **Migration**:
	- Support parallel versions (v1, v2)
	- Use semantic versioning
	- Document breaking changes
- **Best Practices**:
	- Communicate changes early and clearly
	- Use versioning in URI, headers, or query params
	- Test all versions before release

💻 Example (Versioned Endpoints):
```http
GET /api/v1/users
GET /api/v2/users
```

💻 Example (Deprecation Header):
```http
Deprecation: true
Sunset: Wed, 21 Aug 2026 00:00:00 GMT
```

💻 Example (Laravel Versioned Routes):
```php
// routes/api.php
Route::prefix('v1')->group(function () {
		Route::get('/users', [UserController::class, 'indexV1']);
});
Route::prefix('v2')->group(function () {
		Route::get('/users', [UserController::class, 'indexV2']);
});
```

### Working with Third Party APIs

🔹 Concept
- **Third-Party APIs**: Integrate external services (payment, social login, maps, etc.) into your app.
- **API Keys Management**:
	- Store keys securely (env variables, secrets manager)
	- Rotate keys regularly
- **Rate Limits**:
	- Respect provider limits to avoid blocking
	- Implement retry/backoff logic
- **SDK Usage**:
	- Use official SDKs for easier integration
	- Read provider docs for best practices
- **Error Handling**:
	- Handle provider errors gracefully
	- Log failed requests for troubleshooting
- **Best Practices**:
	- Monitor usage and costs
	- Secure sensitive data
	- Document integration steps

💻 Example (Node.js with Stripe SDK):
```js
const stripe = require('stripe')(process.env.STRIPE_KEY);
stripe.charges.create({
	amount: 2000,
	currency: 'usd',
	source: 'tok_visa',
	description: 'Charge for ayush@example.com',
});
```

💻 Example (API Key in Request Header):
```http
GET /api/data
X-API-Key: your_api_key_here
```

💻 Example (Laravel HTTP Client for Third-Party API):
```php
$response = Http::withHeaders([
		'X-API-Key' => env('THIRD_PARTY_KEY'),
])->get('https://thirdparty.com/api/data');
if ($response->successful()) {
		// Process data
} else {
		\Log::error('Third-party API error', ['status' => $response->status()]);
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Aggregation and Orchestration

🔹 Concept
- **API Aggregation**: Combine data from multiple APIs into a single response.
- **Orchestration**: Coordinate multiple API calls, transform and merge results.
- **Use Cases**:
	- Dashboard combining data from several services
	- Backend-for-frontend pattern
	- Data enrichment
- **Techniques**:
	- Parallel requests for speed
	- Data transformation/mapping
	- Error handling and fallback logic
- **Best Practices**:
	- Cache aggregated results if possible
	- Handle partial failures gracefully
	- Document data sources and transformations

💻 Example (Node.js Aggregation):
```js
const axios = require('axios');
const getUserAndOrders = async (userId) => {
	const [userRes, ordersRes] = await Promise.all([
		axios.get(`/api/users/${userId}`),
		axios.get(`/api/orders?user=${userId}`)
	]);
	return {
		user: userRes.data,
		orders: ordersRes.data
	};
};
```

💻 Example (Orchestration with Fallback):
```js
async function getProfile(userId) {
	try {
		const user = await axios.get(`/api/users/${userId}`);
		const posts = await axios.get(`/api/posts?user=${userId}`);
		return { user: user.data, posts: posts.data };
	} catch (err) {
		// Fallback to cached data
		return getCachedProfile(userId);
	}
}
```

💻 Example (Laravel Aggregation with HTTP Client):
```php
// Aggregate user and order data from two APIs
$user = Http::get('https://api.example.com/users/1')->json();
$orders = Http::get('https://api.example.com/orders?user=1')->json();
return [
		'user' => $user,
		'orders' => $orders
];
```




<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Real World API Examples

🔹 Concept
- **Real-world APIs**: Practical examples of common API patterns, request/response formats, and best practices.
- **Patterns**:
	- CRUD operations
	- Authentication
	- Pagination
	- Error handling
	- Filtering & sorting

💻 Example (User CRUD - REST):
```http
POST /api/users
Content-Type: application/json

{
	"name": "Ayush",
	"email": "ayush@example.com"
}
```
Response:
```json
{
	"id": 1,
	"name": "Ayush",
	"email": "ayush@example.com"
}
```

💻 Example (Authentication - JWT):
```http
POST /api/login
{
	"email": "ayush@example.com",
	"password": "secret"
}
```
Response:
```json
{
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6..."
}
```

💻 Example (Paginated List):
```http
GET /api/products?page=2&limit=10
```
Response:
```json
{
	"data": [ ... ],
	"meta": {
		"total": 100,
		"page": 2,
		"limit": 10
	}
}
```

💻 Example (Error Response):
```json
{
	"error": {
		"code": 404,
		"message": "Product not found"
	}
}
```

💻 Example (Laravel CRUD Controller):
```php
// app/Http/Controllers/ProductController.php
public function store(Request $request) {
		$product = Product::create($request->all());
		return response()->json($product, 201);
}
public function index(Request $request) {
		return Product::paginate(10);
}
public function show($id) {
		$product = Product::findOrFail($id);
		return response()->json($product);
}
public function destroy($id) {
		Product::destroy($id);
		return response()->json(null, 204);
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### API Design Case Studies

🔹 Concept
- **Case studies**: Analysis of popular APIs and their design decisions.
- **Twitter API**:
	- RESTful endpoints, rate limits, OAuth authentication
	- Example: `GET /2/tweets?ids=123,456`
- **GitHub API**:
	- REST & GraphQL, pagination, error formats
	- Example: `GET /repos/{owner}/{repo}/issues`
- **Stripe API**:
	- Versioned endpoints, idempotency keys, webhooks
	- Example: `POST /v1/charges`
- **Lessons Learned**:
	- Consistent resource naming
	- Clear error messages
	- Use of standards (OAuth, JSON:API)
	- Good documentation and onboarding

💻 Example (Stripe Payment - Node.js):
```js
const stripe = require('stripe')(process.env.STRIPE_KEY);
stripe.charges.create({
	amount: 2000,
	currency: 'usd',
	source: 'tok_visa',
	description: 'Charge for ayush@example.com',
});
```

💻 Example (Laravel Stripe Integration):
```php
// app/Http/Controllers/PaymentController.php
public function charge(Request $request) {
		$stripe = new \Stripe\StripeClient(env('STRIPE_KEY'));
		$charge = $stripe->charges->create([
				'amount' => 2000,
				'currency' => 'usd',
				'source' => $request->input('token'),
				'description' => 'Charge for ' . $request->input('email'),
		]);
		return response()->json($charge);
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Building Your First API Project

🔹 Concept
- **End-to-end API development walkthrough**: Steps to build, test, and deploy a complete API project.
- **Steps**:
	1. Define requirements and data models
	2. Set up project structure (framework, folders)
	3. Implement endpoints (CRUD, auth, etc.)
	4. Add validation, error handling, middleware
	5. Integrate with database
	6. Write tests (unit, integration)
	7. Document API (OpenAPI, Scribe)
	8. Set up CI/CD pipeline
	9. Deploy to production

💻 Example (Node.js Express Project Structure):
```text
project/
	├── controllers/
	├── models/
	├── routes/
	├── middleware/
	├── tests/
	├── app.js
	└── package.json
```

💻 Example (Express.js CRUD Route):
```js
app.post('/api/products', (req, res) => {
	// Create product
});
app.get('/api/products', (req, res) => {
	// List products
});
```

💻 Example (Laravel API Project Skeleton):
```text
project/
	├── app/Http/Controllers/
	├── app/Models/
	├── routes/api.php
	├── database/migrations/
	├── tests/Feature/
	├── composer.json
	└── .env
```

💻 Example (Laravel API Endpoint):
```php
// routes/api.php
Route::apiResource('products', ProductController::class);

// app/Http/Controllers/ProductController.php
public function store(Request $request) {
		$product = Product::create($request->all());
		return response()->json($product, 201);
}
public function index() {
		return Product::all();
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->
