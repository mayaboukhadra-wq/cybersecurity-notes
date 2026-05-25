# 🌐 Network Protocols: HTTP & HTTPS Exploration

Welcome to my cybersecurity documentation! As part of my structured learning towards becoming a **SOC Analyst**, I completed the **HTTP in Detail** module on TryHackMe. This repository documents my hands-on experience using **Kali Linux** to analyze web traffic protocols.

---

## 🧠 Core Technical Concepts Learned

### 1. The Client-Server Architecture
* **Client:** The initiator of the request (e.g., Firefox browser, or command-line tools like `curl`).
* **Server:** The remote host that processes the request and responds with assets (e.g., HTML, CSS, JSON, Images).

### 2. HTTP Request Structure
An HTTP request sent by a client consists of:
* **Request Methods (Actions):**
  * `GET`: Retrieves data from a server (e.g., viewing a web page).
  * `POST`: Submits new data (e.g., sending credentials securely in a `/login` page inside the HTTP Body).
  * `PUT`: Updates existing records (e.g., changing an email address).
  * `DELETE`: Removes data from the server.
* **Request Headers:** Metadata giving context about the client (e.g., `User-Agent: curl/8.18.0` identifies the tool being used).

### 3. HTTP Response Structure
The server's response to the client contains:
* **Status Codes:** Critical 3-digit numbers indicating the operation's outcome:
  * `200 OK`: Request succeeded.
  * `301/302`: Redirection to another URL.
  * `403 Forbidden`: Access denied.
  * `404 Not Found`: Page or asset does not exist.
  * `500 Internal Server Error`: Server-side application crash.
* **Response Headers:** Information about the server and payload (e.g., `Content-Type: text/html`, `Content-Length`).

---

## 🛡️ Security Perspective: HTTP vs. HTTPS

* **HTTP (Plaintext):** Transmits data in clear text. Highly vulnerable to **Man-in-the-Middle (MitM)** sniffing attacks via tools like Wireshark.
* **HTTPS (Encrypted):** Uses **TLS/SSL** to encrypt the communication channel. It secures sensitive data (like session cookies and passwords) and verifies the server's identity using **Digital Certificates**.

---

## 💻 Hands-on Lab: Analyzing Live Headers via `curl`

I used `curl` in my Kali Linux terminal to inspect actual HTTP headers from live servers.

### Task 1: Inspecting Response Headers Only
Command used:
```bash
curl -I [https://www.google.com](https://www.google.com)                                              curl -I https://www.google.com
Task 2: Tracking the Complete Verbose Flow
Command used:

Bash

curl -v https://httpbin.org/get
🎯 SOC Analyst Takeaway
Monitoring and reading HTTP logs is a fundamental daily task for a security analyst. By understanding "normal traffic" patterns (like proper headers and status codes), I can effectively spot malicious anomalies such as Brute Force attempts (excessive POST requests to /login) or Web Attacks (malicious inputs injected inside query strings).
