# Proxy Server

## What is a Proxy?

A **Proxy Server** is an intermediate server that sits between a client (like a web browser) and the internet. It forwards client requests to other servers and can return responses either from its cache or from the actual target server.

## How a Proxy Works

1. The client sends a request to the proxy server.
2. The proxy evaluates the request.
3. The proxy forwards the request to the destination server or serves it from cache.
4. The proxy returns the response to the client.

## Types of Proxies

### 1. **Forward Proxy**
- Positioned between client and internet.
- Hides the client's identity.
- Commonly used for security, content filtering, or anonymous browsing.

### 2. **Reverse Proxy**
- Positioned in front of web servers.
- Hides the server's identity.
- Often used for load balancing, caching, and SSL termination.

### 3. **Transparent Proxy**
- Does not modify requests or responses.
- Often used for content filtering and monitoring without user knowledge.

### 4. **Anonymous Proxy**
- Hides the client's IP address but identifies itself as a proxy.

### 5. **High Anonymity Proxy**
- Hides both the client's IP and the fact that it's a proxy.

## Benefits of Using a Proxy

- 🛡️ **Security**: Protects internal networks from external threats.
- 🌐 **Anonymity**: Hides client IP addresses for privacy.
- 🚀 **Performance**: Caches frequently accessed content.
- ⚖️ **Load Balancing**: Distributes requests across multiple servers.
- 📑 **Access Control**: Restricts access to certain websites or services.

## Real-World Use Cases

- Bypassing geo-restrictions
- Corporate content filtering
- DDoS protection
- Logging and monitoring
- Web scraping

## Proxy vs VPN

| Feature       | Proxy                          | VPN                          |
|---------------|-------------------------------|------------------------------|
| Encryption    | Usually not encrypted          | Fully encrypted              |
| Speed         | Generally faster               | Can be slower due to encryption |
| IP Masking    | Yes                            | Yes                          |
| System Scope  | App-specific                   | System-wide                  |

## Summary

A **proxy server** acts as a gateway between users and the internet, offering security, performance optimization, and privacy. Depending on the type, it can serve very different purposes, from anonymizing clients to distributing load on backend systems.

