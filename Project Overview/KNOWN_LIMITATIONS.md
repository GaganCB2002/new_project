# Known Limitations

## Incomplete Modules
- **Payroll Integration:** Currently calculates values but does not dispatch real banking API calls.
- **Mobile App:** Placeholder folder exists, but full Flutter/React Native implementation is pending.

## Technical Debt
- **Frontend Monolith:** The frontend is a large SPA. As more roles are added, bundle size optimization and micro-frontends might be required.
- **Dual Backend Maintenance:** Maintaining both Node.js and Spring Boot requires dual-stack expertise.

## Performance Issues
- The `AttendanceCalendar` fetches large amounts of raw data; needs pagination or aggregation at the database level.
- LiveGuard telemetry can spam the database if Kafka consumers are not properly batching inserts.
