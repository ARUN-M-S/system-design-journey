# Load Balancer

Load balancing is the process of distributing network traffic across multiple servers to ensure no single server becomes a bottleneck, ensuring high availability, reliability, and scalability.

## 📦 Why Load Balancing?

Handles increased user traffic.

Avoids single points of failure.

Improves response time and performance.

### ⚙️ Load Balancing Algorithms

#### 1. Round Robin

Distributes client requests sequentially across the server pool.

Example:
If you have 3 servers and 6 users, each server gets 2 users in order: S1 → S2 → S3 → S1 → S2 → S3

Used by: Swiggy, Dream11 (for general traffic distribution)

#### 2. Weighted Round Robin

Same as round robin, but assigns more traffic to powerful servers.

Example:
If S1 has twice the resources of S2 and S3, then S1 gets 2x more requests.

Used by: Content-heavy apps like YouTube, Netflix.

#### 3. Least Connections

Routes requests to the server with the fewest active connections.

Best for: Long-lived connections like WebSockets or streaming apps.

Used by: Zoom, Google Meet

#### 4. Least Response Time

Sends traffic to the server with the lowest response time and fewer active connections.

Best for: Real-time systems like stock trading apps.

#### 5. IP Hash / URL Hash

A hash of the client IP or URL path determines the server.

Used for: Sticky sessions or path-based routing.

E-commerce Example:

/cart → routed to Cart DB

/wishlist → Wishlist DB

/gadgets/mobile → Product DB

#### 6. Sticky Sessions (Session Persistence)

Ensures the same user connects to the same server.

Best for: When app state is stored locally on a server.

Used by: Banking applications, online exam systems

#### 🧠 Advanced Routing - Path Based

Path-based routing is used by apps like Amazon, Flipkart:

/user → User Service

/cart → Cart Service

/payment → Payment Service

Each can hit different backend microservices or databases.

#### 🔍 Real-World Examples

App

#### Likely Strategy

Swiggy

Round Robin, Sticky Sessions

Google Maps

Least Connections + Geo Load Balancing

Dream11

Weighted Round Robin, Session Persistence

Amazon

Path-Based Routing, Sticky + IP Hash

Flipkart

Path-Based + Least Response Time

#### 🚀 How to Choose an Algorithm?

Need

Best Algorithm

Even traffic distribution

Round Robin

High capacity servers

Weighted Round Robin

Real-time apps

Least Connections/Response

Sticky sessions (login states)

Sticky Sessions/IP Hash

E-commerce path handling

Path-Based + URL Hash

#### 🛠️ Do Servers (like RedHat) Support These?

Yes! Most enterprise Linux distributions and cloud load balancers (AWS ELB, NGINX, HAProxy) support these algorithms and let you choose/configure them per use-case.

## 🌍 Is One DB Enough?

No — you need to:

Scale DB with read replicas

Use sharding based on customer region (e.g., IN, EU, US)

Cache popular queries (Redis, CDN)

#### 🔁 Request Flow Example

User opens Flipkart app.

DNS resolves to nearest edge (CDN)

Load Balancer routes request via path /mobiles to Product Service.

Product Service calls DB or Redis for listing.

#### 🧭 Summary

Load balancing is vital for scaling systems.

Choose algorithm based on use-case.

Path-based routing and microservice mapping help large apps scale efficiently.

Don’t forget to scale your DB and cache layers.

