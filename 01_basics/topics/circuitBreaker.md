# 🔌 Circuit Breaker — Resilience Module for Microservices

This module implements the **Circuit Breaker pattern** to enhance fault tolerance in distributed systems. It is designed to **protect critical services** from cascading failures by stopping calls to a failing service temporarily and restoring them when the service becomes healthy.

---

## 📐 Why Circuit Breaker?

In a microservices-based architecture, dependencies can fail. Constantly retrying failing services leads to:

- Resource exhaustion
- Slower system performance
- Worsening outages (cascading failures)

The **Circuit Breaker** prevents this by:

- Detecting repeated failures
- Breaking the circuit (fail-fast)
- Allowing self-healing after a cooldown period

---

## 🔧 How It Works

### States:

| State        | Description                                                       |
|--------------|-------------------------------------------------------------------|
| **Closed**   | Normal flow. Requests are allowed. Failures are tracked.          |
| **Open**     | Requests are blocked immediately. After a timeout, it moves to... |
| **Half-Open**| A trial request is sent. If successful, circuit closes.           |

### Transition Diagram:

[CLOSED] --(failures > threshold)--> [OPEN]
[OPEN] --(timeout expires)--> [HALF-OPEN]
[HALF-OPEN] --(success)--> [CLOSED]
[HALF-OPEN] --(failure)--> [OPEN]


---

## 🔨 Use Case in System Design

- Wrap API calls to external services like Payment, Email, Search, or User Profile.
- Apply in API Gateway or service mesh layer (e.g., sidecar in Istio).
- Can be combined with retry strategies and fallbacks.

---

## 🛠️ Configuration

```js
const breaker = new CircuitBreaker({
  failureThreshold: 3,     // Break after 3 failures
  successThreshold: 2,     // Close after 2 successes
  timeout: 10000           // Stay open for 10 seconds
});
 ```

## 🧪 Example Usage

breaker.fire(async () => {
  const response = await fetch('https://api.partner-service.com/data');
  return await response.json();
})
.then(data => console.log('Success:', data))
.catch(err => console.error('Breaker Open:', err.message));

## ⚙️ Integration Points
Inside any microservice handling outbound HTTP/database calls

As a wrapper in API layer (BFF)

In Node.js middleware or Express service gateway


## 📚 References
Martin Fowler: Circuit Breaker

Resilient Systems Design