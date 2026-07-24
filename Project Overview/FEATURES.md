# Features List

## 1. Unified Dashboarding
- **Purpose:** Provide role-specific overviews.
- **Users:** All Roles.
- **Implementation:** Dynamic component rendering based on JWT claims.

## 2. Real-Time Telemetry & GPS (LiveGuard)
- **Purpose:** Track remote worker location and system vitals.
- **Users:** HR, Security Analyst, Managers.
- **Implementation:** Desktop agent sending Websocket/Kafka events to Node backend, visualized on React-Leaflet maps.

## 3. Automated Payroll & Compensation
- **Purpose:** Seamless salary disbursement.
- **Users:** Finance Manager, HR.
- **Implementation:** Scheduled CRON jobs calculating base pay + overtime - deductions.

## 4. Attendance & Timesheets
- **Purpose:** Track working hours.
- **Users:** Employees, HR.
- **Implementation:** Clock-in/out widgets with IP/Geolocation validation.

## 5. Security & Audit Logging
- **Purpose:** Track every sensitive action.
- **Users:** Security Analyst, CTO.
- **Implementation:** Global middleware logging actions to a specialized `AuditLog` table.

## 6. Project & Task Orchestration
- **Purpose:** Manage engineering and marketing deliverables.
- **Users:** Project Manager, Software Engineer, QA.
- **Implementation:** Kanban boards via ReactFlow and custom drag-and-drop interfaces.
