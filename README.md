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

# Secure-JSON-RPC-Message wrapper
SJRM can add per-message security features to JSON-RPC communications for Model Context Protocol.

SJRM enhances it by adding:
  Message integrity & authentication using HMAC (a secure cryptographic tag per message)
  
  Replay protection with unique nonces and strict timestamps — so old or repeated messages get blocked
  
  Sender authentication via JWT tokens which also help generate secure keys
  
  Version negotiation so different systems can agree on which SJRM version to use

  

Key Features



  Works seamlessly with both single and batch JSON-RPC requests
  
  Lightweight enough for high-performance microservices
  
  Detects tampering, expired messages, and replay attacks
  
  Easy to integrate with existing JSON-RPC based systems
  
  Flexible and extendable for future improvements



  This Python code is a reference implementation of the Secure JSON-RPC Message (SJRM) Protocol v1.0 intended to illustrate the core concepts and workflow. It is not production-ready and may require further enhancements for security, performance, and scalability in real-world deployments. Users are encouraged to review, test, and improve the code according to their specific requirements and threat models.
