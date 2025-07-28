# Secure-JSON-RPC-Message
Adds per-message security features to JSON-RPC 2.0 communications for distributed systems and multi-agent platforms.

JSON-RPC 2.0 is a popular protocol for remote procedure calls, but it doesn’t secure each message on its own.
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
