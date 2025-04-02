## 🔐 ECC-Based Secure Communication Protocol

This project implements a secure communication protocol using **Elliptic Curve Cryptography (ECC)**, focusing on **ephemeral key exchange**, **digital certificates**, **HMAC**, and **AES-256 encryption**. It was developed as a reference implementation for the protocol described in the [JCP paper](https://www.mdpi.com/2624-800X/5/2/11).

---

### 📁 Project Structure

```
.
├── keys/                  # ECC private and public keys
├── certs/                 # X.509 certificates and CSRs
├── server.c               # Server-side implementation
├── client.c               # Client-side implementation
├── ca_generate_keys.sh    # Bash script to generate CA, client, and server certs
├── Makefile               # Build, run, clean utilities
└── README.md              # This file
```

---

### 🔧 Features

- **Ephemeral ECC Key Exchange** using `secp256k1`
- **X.509 Certificates** for client/server authentication
- **AES-256-CBC** for symmetric encryption
- **SHA-3-256** for shared key derivation
- **HMAC-SHA256** for message integrity
- **Time-based session key generation**
- **Detailed performance timing logs**

---

### 🧪 How to Run

#### 1. 🔑 Generate Certificates and Keys
```bash
make keys
```

#### 2. 🛠️ Compile Server and Client
```bash
make all
```

#### 3. 🖥️ Run the Server
```bash
make run-server
```

#### 4. 💻 Run the Client (in a new terminal)
```bash
make run-client
```

---

### 📊 Performance Metrics

Both client and server log the time taken (in milliseconds) for:

- Certificate signing/verification
- Shared key derivation
- HMAC generation and validation
- AES encryption/decryption
- Total protocol runtime

---

### 📄 Paper Reference

> **Title:** A Lightweight ECC-Based Mutual Authentication Protocol with Key Agreement for Smart Devices  
> **Journal:** Journal of Cybersecurity and Privacy (2021)  
> **DOI:** [10.3390/jcp5010011](https://www.mdpi.com/2306-5729/5/1/11)

This implementation closely follows the sequence of steps and cryptographic methods proposed in the paper.

---

### 🧱 Requirements

- `OpenSSL` library (`libssl-dev`)
- `gcc`
- POSIX-compliant system (Linux/macOS)

---

### 🗼 Clean Up

```bash
make clean
```

