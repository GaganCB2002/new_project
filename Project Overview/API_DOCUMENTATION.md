# API Documentation

## Authentication Endpoints
- `POST /api/auth/login` - Returns JWT token.
- `POST /api/auth/refresh` - Refreshes session token.

## HR Endpoints
- `GET /api/hr/employees` - List all employees (HR only).
- `POST /api/hr/employees` - Onboard new employee.
- `GET /api/hr/attendance` - Get attendance aggregations.

## Finance Endpoints
- `POST /api/finance/payroll/run` - Trigger batch payroll calculation.
- `GET /api/finance/expenses` - List pending expenses.

## Telemetry Endpoints (High Throughput)
- `POST /api/telemetry/gps` - Ingest agent GPS data.
- `WS /ws/liveguard` - Real-time websocket feed for command center.

## Project Management Endpoints
- `GET /api/projects/tasks` - List user tasks.
- `PUT /api/projects/tasks/:id/status` - Update task state.

**Common Error Codes:**
- `401 Unauthorized`: Missing JWT.
- `403 Forbidden`: Insufficient RBAC permission.
- `404 Not Found`: Resource missing.
- `429 Too Many Requests`: Rate limit exceeded.
