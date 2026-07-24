# Security Architecture

## Authentication
- Stateless JWT tokens with short expiration (15m) and rotating refresh tokens (7d).

## Authorization (RBAC)
- Strict middleware on every route verifying the user's `Role` enum against the endpoint's required permissions.

## Encryption
- Passwords hashed with bcrypt (cost factor 12).
- Data at rest encrypted via cloud provider volumes.
- Data in transit encrypted via TLS 1.3 (HTTPS/WSS).

## Audit Logging
- ALL mutating requests (POST, PUT, DELETE) are logged asynchronously to the `AuditLog` table, capturing UserID, IP, Action, and Payload diff.

## API Security
- Helmet.js for secure HTTP headers.
- Rate limiting implemented via Redis.
