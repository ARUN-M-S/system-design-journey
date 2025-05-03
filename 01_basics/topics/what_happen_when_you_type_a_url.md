# What Happens When You Type a URL?

When you type a URL like `https://www.google.com` into your browser and press Enter, a lot happens behind the scenes. This process involves multiple systems including DNS, TCP/IP, HTTP, and your browser rendering engine.

---

## 🌐 Step-by-Step Process

### 1. URL Parsing

The browser breaks down the URL into parts:

- **Protocol**: `https`
- **Hostname**: `www.google.com`
- **Path**: `/` (default if not specified)

---

### 2. Browser Cache Check

Before going to the internet, the browser checks its own cache:

- ✅ If content is cached and fresh → serve directly.
- ❌ If not cached or expired → move to DNS lookup.

---

### 3. DNS Resolution

The browser needs to translate the domain into an IP address:

- Checks local DNS cache.
- If not found, asks the configured DNS resolver.
- Resolver finds and returns IP address (e.g., `142.250.183.36`).

---

### 4. Establish TCP Connection

The browser initiates a **TCP handshake** with the server's IP on:

- **Port 80** → for HTTP  
- **Port 443** → for HTTPS

---

### 5. TLS Handshake (if HTTPS)

For secure connections:

- Browser and server perform a TLS handshake.
- Exchange certificates and keys.
- Establish an encrypted session.

---

### 6. Send HTTP Request

The browser sends a request like:

```http
GET / HTTP/1.1
Host: www.google.com
User-Agent: Chrome/...
Accept: text/html 

```


### 7. Server Processes Request

The web server:

May interact with databases or microservices.

Prepares the response (HTML/CSS/JS/images).

Sends it back to the browser.


### 8. HTTP Response Returned
Example response:

```http
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: ...
```

### 9. Browser Rendering
The browser:

Parses HTML.

Loads and applies CSS.

Executes JavaScript.

Renders the final UI.

### 10. Additional Requests
For CSS, JS, fonts, images, etc., the browser:

Sends more requests.

Caches resources as per Cache-Control, ETag, etc.

## 📊 Summary Table

| Step                | Description                                |
|---------------------|--------------------------------------------|
| URL Parsing         | Splits URL into protocol, host, path       |
| Cache Check         | Looks for cached content                   |
| DNS Resolution      | Resolves domain name to IP address         |
| TCP Connection      | Opens a TCP connection to server           |
| TLS Handshake       | Sets up secure encryption (HTTPS only)     |
| HTTP Request        | Sends request to server                    |
| Server Processing   | Handles logic and prepares response        |
| HTTP Response       | Sends back data (HTML/CSS/JS)              |
| Rendering           | Browser renders UI                         |
| Additional Requests | Fetches assets like CSS, JS, images        |
