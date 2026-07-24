# System Design

## Architecture Flow
1. **Client Layer:** Web App (React) / Desktop Agent / Mobile App.
2. **API Gateway:** Nginx / Kubernetes Ingress routes traffic based on path (`/api` to Node, `/java` to Spring Boot).
3. **Application Layer:** 
   - Node.js handles I/O heavy tasks (Sockets, simple CRUD).
   - Java handles CPU heavy tasks (Complex reports, payroll algorithms).
4. **Event Bus:** Kafka queues telemetry and audit logs to prevent database locking.
5. **Data Layer:** PostgreSQL (Persistent), Redis (Ephemeral/Cache).

## Application Lifecycle
- Frontend loads static assets via CDN.
- React Router determines the lazy-loaded chunk based on user role.
- Redux hydrates state via initial `/api/auth/me` call.
- WebSockets initialize for real-time notifications.
