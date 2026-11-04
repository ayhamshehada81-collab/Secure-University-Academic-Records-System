[README.md](https://github.com/user-attachments/files/34385875/README.md)
# Secure University Academic Records System

Course 906313 - Information and Database Security, Al al-Bayt University, First Semester 2026/2027.

**Group:** Ameen Thybat, Ayham Shehada

A university application (students, lecturers, courses, sections, enrolments, grades) built from scratch to demonstrate a secure database and application: Oracle AI Database Free 26ai, Java 21 + Spring Boot 3 + Spring Security, React + Vite. All data is fictional.

## Roles
Student, Lecturer, Registrar, Security Auditor (see `docs/M1/M1_Requirements.pdf`).

## Repository structure
```
backend/        Spring Boot project
frontend/       React + Vite project
db/             01_admin_setup.sql, 02_schema.sql, 03_seed.sql
db/security/    users_roles.sql, api_packages.sql, vpd.sql, audit.sql
db/recovery/    export_import_steps.md, verify.sql, mask.sql
lab/            isolated_SQLi_demo/, README_SAFETY.md
docs/           M1/ M2/ M3/ M4/ FinalReport.pdf
evidence/       screenshots/, test_log.xlsx, sanitized_logs/
contribution/   individual_contributions.pdf
```

## Release plan
| Tag | Date | Content |
|---|---|---|
| M1 | 06/11/2026 | Requirements, ERD, Architecture/DFD, STRIDE, team plan, this README |
| M2 | 20/11/2026 | SQL scripts 01-03, Spring Boot + React with login, functional tests |
| M3 | 11/12/2026 | RBAC, least privilege, VPD, SQLi lab and fix, auditing/FGA, hardening, tests T1-T10 |
| FINAL | 25/12/2026 | TDE or TCPS, backup/restore/masking, tests T1-T13, final report |

## Running the project (completed in M2)
1. Install Oracle AI Database Free (service `FREEPDB1`), JDK 21, Maven, Node.js LTS, Git.
2. Run `db/01_admin_setup.sql`, `02_schema.sql`, `03_seed.sql`, then `db/security/*` in the documented order.
3. Copy `.env.example` to `.env` and set the database URL and `APP_USER` credentials (never commit `.env`).
4. Backend: `cd backend && mvn spring-boot:run`. Frontend: `cd frontend && npm install && npm run dev`.

## Safety
Attacks and scans are allowed only against the separate `ARS_LAB` schema on the group's own local network. No secrets, wallets or real data are committed.
