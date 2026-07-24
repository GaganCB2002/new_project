# Database Schema

## ER Diagram (Mermaid)
```mermaid
erDiagram
    USER ||--o{ ATTENDANCE : logs
    USER ||--o{ PAYROLL : receives
    USER ||--o{ ACTIVITY_LOG : generates
    USER ||--o{ MESSAGE : sends
    USER {
        uuid id PK
        string email
        string role
        string status
    }
    ATTENDANCE {
        uuid id PK
        uuid userId FK
        datetime checkIn
        datetime checkOut
        string location
    }
    PAYROLL {
        uuid id PK
        uuid userId FK
        float amount
        string status
    }
    ACTIVITY_LOG {
        uuid id PK
        uuid userId FK
        string action
        datetime timestamp
    }
```

## Key Tables
- **Users / Employees:** Core identity records.
- **Attendance:** Timestamps for work sessions.
- **Payroll:** Monthly salary generation records.
- **Activity_Log (AuditLog):** Immutable ledger of sensitive actions.
- **Telemetry:** High-volume time-series data for GPS and system monitoring (often partitioned).
