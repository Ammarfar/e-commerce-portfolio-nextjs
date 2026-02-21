# PRD — Portfolio Microservice Platform (Phase 1)

## AI Assisted Product Catalog Service

A backend portfolio project that simulates modern e-commerce platform, built phase by phase.

**Phase 1 highlights:**

* **AI integration**:
AI assistant that can answer product questions and generate recommendations using real product data.

* **High-traffic readiness via caching**:
Implements Redis caching and pagination strategies to handle million of products, demonstrating performance awareness and real-world read optimization patterns.

* **Background large data handling**:
Features resumable CSV batch import to demonstrate concurrency, job lifecycle management, and working with large-scale data safely.

---

# Features & Scope

### 1) AI Assistant Integration

* Answer product-related questions
* Suggest recommendations
* Add product to cart
* Cannot modify product data

### 2) Product Catalog Service

* Create, update, delete products (Admin only)
* Product listing with cursor-based pagination (Lazy loading)
* Product detail
* Search by name or category
* Filter by category & price range

### 3) Shopping Cart

* Add and remove product to cart
* View cart contents with total amount to be paid
* Update quantity
* Without checkout or order workflow yet

### 4) Batch CSV import

* CSV template download
* CSV upload
* Progress tracking
* Pause, Resume, Cancel import

### 5) Authentication & RBAC

* Login
* Register
* Roles:
  * Admin → manage products & import
  * User → read products

---

# User flow

### 1) Normal User Journey

```
Login
→ Browse products (infinite scroll)
→ Add to cart
→ Search/filter products
→ Open product detail
→ Add to cart
→ Open cart drawer
→ Ask chatbot for recommendations (floating widget)
→ Add suggested item to cart
```

---

### 2) Admin Journey

```
Login as Admin
→ Create/Edit/Delete product (modal)
→ Open Import page
→ Download template
→ Upload CSV
→ Monitor progress
→ Cancel/Pause/Resume if needed
```

---

# C. Phase roadmap (context only)

| Phase   | Focus                                 |
| ------- | ------------------------------------- |
| Phase 1 | Product & cart + AI chatbot           |
| Phase 2 | LLM image verification                |

---
