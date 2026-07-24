# Platform Workflows

## Authentication Workflow
1. User enters credentials.
2. Backend validates bcrypt hash.
3. Backend checks role and department.
4. JWT is generated and returned as HttpOnly cookie.
5. Frontend redirects to role-specific dashboard (e.g., `/ceo`, `/hr`, `/software-engineer`).

## Attendance Workflow
1. Employee clicks "Clock In".
2. Browser captures Geolocation.
3. API validates IP/Location against geofences.
4. Attendance record created.
5. Real-time event pushed to HR Dashboard.

## Payroll Workflow
1. HR approves timesheets.
2. Finance clicks "Run Payroll".
3. Java backend aggregates attendance, applies tax formulas.
4. Payroll records generated.
5. PDFs generated and emailed to employees.
