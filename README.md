Here is your full `README.md` file with the **logo badge**, project information, and all other content formatted using Markdown:

---

```markdown
<p align="center">
  <img src="https://img.shields.io/badge/Secure%20JSON--RPC%20Wrapper-%F0%9F%94%92-blue?style=for-the-badge&logo=python&logoColor=white" alt="Secure JSON-RPC Wrapper Badge"/>
</p>

<h1 align="center">Secure JSON-RPC Message Wrapper</h1>
<p align="center">
  <strong>🔐 Secure your JSON-RPC messages with AES-GCM and HMAC-SHA256</strong>
</p>

<p align="center">
  <a href="https://github.com/shalak97/Secure-JSON-RPC-Message-Wrapper">
    <img src="https://img.shields.io/github/stars/shalak97/Secure-JSON-RPC-Message-Wrapper?style=flat-square" alt="GitHub Stars">
  </a>
  <a href="https://github.com/shalak97/Secure-JSON-RPC-Message-Wrapper">
    <img src="https://img.shields.io/github/last-commit/shalak97/Secure-JSON-RPC-Message-Wrapper?style=flat-square" alt="Last Commit">
  </a>
  <img src="https://img.shields.io/badge/License-MIT-green.svg?style=flat-square" alt="MIT License">
</p>

---

## 📌 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Cryptographic Standards](#cryptographic-standards)
- [Installation](#installation)
- [Usage](#usage)
- [Message Structure](#message-structure)
- [Security Considerations](#security-considerations)
- [Project Structure](#project-structure)
- [Testing](#testing)
- [License](#license)
- [Contributing](#contributing)
- [Contact](#contact)

---

## 📖 Overview

JSON-RPC is a stateless, lightweight remote procedure call (RPC) protocol. However, native JSON-RPC does not implement security features such as encryption or authentication.

This wrapper adds **AES encryption**, **HMAC signing**, and **nonce-based replay protection** to JSON-RPC messages using the following steps:

- Encrypts payload using **AES-GCM** (authenticated encryption)
- Attaches a cryptographic signature (HMAC-SHA256)
- Wraps it in a structured envelope with metadata (nonce, timestamp, version)

---

## ✨ Features

- 🔒 AES-GCM Encryption for confidentiality
- ✍️ HMAC-SHA256 Signing for integrity and authenticity
- 🕓 Nonce + Timestamp-based Replay Protection
- ⚙️ Pluggable Crypto Layer
- 🧪 Ready-to-use Python modules with test cases

---

## 🏗️ Architecture

```

Client
|
\|---> \[ JSON-RPC Message ]
\|         ↓
\|---> \[ Encrypt + Sign + Wrap ]
\|         ↓
\|---> \[ Secure JSON-RPC Envelope ]
\|         ↓
\|-------> Server

Server
|
\|---> \[ Unwrap + Verify Signature + Decrypt ]
\|         ↓
\|---> \[ JSON-RPC Payload ]
\|         ↓
\|---> \[ Execute Procedure ]

````

---

## 🔐 Cryptographic Standards

| Component         | Algorithm     | Purpose              |
|------------------|---------------|----------------------|
| Encryption       | AES-GCM       | Confidentiality & AE |
| Integrity Check  | HMAC-SHA256   | Message Integrity    |
| Replay Defense   | Nonce + Time  | Anti-Replay Attacks  |

---

## ⚙️ Installation

### Prerequisites

- Python 3.8+
- `pip` installed

### Clone the Repository

```bash
git clone https://github.com/shalak97/Secure-JSON-RPC-Message-Wrapper.git
cd Secure-JSON-RPC-Message-Wrapper
````

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🚀 Usage

### Step 1: Create JSON-RPC Payload

```python
payload = {
    "jsonrpc": "2.0",
    "method": "getData",
    "params": {"key": "value"},
    "id": 1
}
```

### Step 2: Encrypt and Wrap

```python
from crypto.wrapper import SecureJSONRPCWrapper

wrapper = SecureJSONRPCWrapper(secret_key=b'securepassphrase123')
secure_message = wrapper.encrypt_and_wrap(payload)
print(secure_message)
```

### Step 3: Verify and Decrypt on Server

```python
received_message = secure_message  # received from client
original_payload = wrapper.unwrap_and_decrypt(received_message)
print(original_payload)
```

---

## 🧾 Message Structure

### Secure Envelope Format

```json
{
  "version": "1.0",
  "timestamp": "2025-08-01T12:00:00Z",
  "nonce": "e7f4c34d...",
  "payload": "<base64_encrypted_json>",
  "hmac": "<base64_signature>"
}
```

* **version**: Wrapper version
* **timestamp**: ISO 8601 UTC time
* **nonce**: Random string for replay protection
* **payload**: AES-GCM encrypted JSON-RPC message (base64)
* **hmac**: HMAC-SHA256 of the entire message (base64)

---

## 🛡️ Security Considerations

* 🔑 **Key Management**: Store AES and HMAC keys securely. Avoid hardcoding in production.
* ⏱️ **Replay Protection**: Validate timestamp and nonce. Consider caching used nonces.
* ✅ **Verify Before Decrypting**: Always check HMAC before decrypting.
* 🕒 **Message Expiry**: Reject messages older than a configured timestamp (e.g., 2 minutes).

---

## 🗂️ Project Structure

```
Secure-JSON-RPC-Message-Wrapper/
├── crypto/
│   ├── __init__.py
│   ├── wrapper.py         # Main wrapper class
│   └── utils.py           # Helper functions
├── tests/
│   ├── test_wrapper.py    # Unit tests
├── requirements.txt
├── README.md
└── LICENSE
```

---

## 🧪 Testing

```bash
pytest tests/
```

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

---

## 🙋‍♂️ Contributing

Contributions are welcome! Feel free to fork the repository, open issues, and submit pull requests.

---

## 📫 Contact

For feedback or questions, feel free to reach out:

* GitHub: [@shalak97](https://github.com/shalak97)


---



Let me know!
```
