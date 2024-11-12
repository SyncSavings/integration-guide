---
title: Security Considerations
nav_order: 4
layout: default
---

## Security Considerations

### Passwordless Experience

- **User Authentication**: Only authenticated users should generate tokens.
- **Session Renewal**: After expiry, users must generate a new token from your platform.

### Secure Data Transfer Mechanism

- **Token Signing**: Use your private key and the RS256 algorithm.
- **Token Verification**: Sync Savings uses your public key to verify tokens.

### Distributor Responsibilities

- Never expose your private key to your front end.
- Ensure accurate and up-to-date user data.
- Implement secure token generation practices.