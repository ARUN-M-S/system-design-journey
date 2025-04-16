# TCP vs UDP

## 📌 What is TCP (Transmission Control Protocol)?

TCP is a **connection-oriented** protocol that ensures reliable data delivery. It establishes a connection between the sender and receiver before transmitting data and verifies that all data reaches its destination.

### 🔑 Key Features:
- Connection-oriented
- Reliable (guarantees delivery)
- Ordered data transfer
- Error checking and correction
- Slower due to overhead

### 📦 Real-life Analogy:
Sending a registered post that needs a signature. You get confirmation that it was delivered successfully.

---

## 🚀 What is UDP (User Datagram Protocol)?

UDP is a **connectionless** protocol that sends data without establishing a connection. It doesn’t guarantee delivery, order, or error checking—making it faster and more lightweight.

### 🔑 Key Features:
- Connectionless
- No delivery guarantees
- No order guarantees
- No error correction
- Very fast

### 📦 Real-life Analogy:
Sending a regular letter. You drop it in the mailbox and hope it arrives.

---

## 🆚 Comparison Table

| Feature           | TCP                            | UDP                        |
|------------------|---------------------------------|----------------------------|
| Type             | Connection-oriented             | Connectionless             |
| Reliability      | Reliable                        | Unreliable                 |
| Ordering         | Guarantees order                | No guarantee               |
| Speed            | Slower                          | Faster                     |
| Overhead         | More (due to acknowledgements)  | Less                       |
| Use Cases        | Web browsing, file transfer     | Streaming, gaming, VoIP    |

---

## 🤝 TCP 3-Way Handshake

Before sending data, TCP establishes a reliable connection using a **three-step handshake**:

1. **SYN**: Client sends a synchronize (SYN) request to the server.
2. **SYN-ACK**: Server acknowledges (ACK) the SYN and sends its own SYN.
3. **ACK**: Client sends back an ACK to confirm.

Now both are connected and ready to transfer data!

### 🔽 Diagram:

```text
Client                      Server
  | ------ SYN -------->    |
  |                         |
  | <----- SYN-ACK ------   |
  |                         |
  | ------ ACK -------->    |
Connection Established ✅
