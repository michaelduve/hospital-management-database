# Hospital Management Database

A production-style PostgreSQL project for managing patients, staff, appointments, admissions, clinical encounters, prescriptions, laboratory orders, billing, payments, and audit events.

## Highlights

- Normalized relational design with UUID keys and strong constraints
- Conflict-safe appointment scheduling
- Clinical and financial separation through PostgreSQL schemas
- Row-level security foundation and least-privilege roles
- Immutable audit trail for sensitive changes
- Operational views for bed occupancy, appointments, and receivables
- Synthetic demonstration data only
- Docker deployment, tests, CI, ER diagram, and runbook

## Quick start

```bash
cp .env.example .env
docker compose up -d
docker compose exec postgres psql -U hospital_app -d hospital
```

Migrations in `database/migrations` and seed files in `database/seeds` run automatically on the first container start.

## Validate

```bash
python scripts/validate_project.py
python -m unittest discover -s tests -v
```

## Privacy

This repository contains no real patient information. Never place production health data in source control. Production use requires jurisdiction-specific privacy review, encryption, private networking, key management, backup testing, access reviews, retention schedules, breach response, and database activity monitoring.

## License

MIT

