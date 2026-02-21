# Technical Design Document (TDD)

# 1. System Overview

## Architecture Design

### Services

1. **Product**

    * Product management
    * CSV Import (pause/resume/cancel)
    * AI Assistant integration

2. **Cart**

    * Cart management

---

## Traffic Characteristics

* Read-heavy workload (product listing dominant)
* Stress metrics defined in Phase 2

---

# 2. Service Boundaries & Data Ownership

| Component       | Responsibility       |
| --------------- | ---------------------|
| Product Service | Products, Import, AI |
| Cart Service    | Cart                 |

---

# 3. Data & API Design

## 3.1 Product Service

### `products`

```
id (uuid)
name
description
price
stock
created_at
updated_at
```

---

### `import_jobs`

```
id (uuid)
status 
progress
current_row
error
created_at
updated_at
```

---

## 3.2 Cart Service

### `cart_items`

```
id (uuid)
user_id
product_id
quantity
created_at
updated_at
```

---

## 3.4 API Endpoints

### Product Service

```
GET    /products
GET    /products/{id}
POST   /products
PUT    /products/{id}
DELETE /products/{id}

POST   /import
GET    /import/{job_id}
POST   /import/{job_id}/pause
POST   /import/{job_id}/resume
POST   /import/{job_id}/cancel

POST   /ai/ask
```

---

### Cart Service

```
GET    /carts/me
POST   /carts/me/items
PUT    /carts/me/items/{item_id}
DELETE /carts/me/items/{item_id}
```

---

# 4. Non-Functional Requirements (NFR)

## Scalability

* Caching
* Lazy loading for product listing

---

## Security

* Authentication
* Role-based authorization

---

## Observability

* OpenTelemetry

---


# 7. Tech Stack

* Next.js
* Drizzle ORM
* Better-auth
* Vercel otel for OpenTelemetry
* Next lazy loading
* Tailwind CSS
