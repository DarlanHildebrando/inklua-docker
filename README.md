# inklua-docker

A Docker Compose setup for the Inklua Ticket system, consisting of a PostgreSQL database, Python backend, Node.js backend, and Next.js frontend.

## Services

- **db**: PostgreSQL 15 database
- **backend-py**: Python backend service (port 8000)
- **backend-node**: Node.js backend service (port 3001)
- **front-end**: Next.js frontend application (port 3000)

## Prerequisites

- Docker
- Docker Compose

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/DarlanHildebrando/inklua-docker.git
cd inklua-docker
```

2. Start all services:
```bash
docker-compose up -d
```

3. Access the application:
   - Frontend: http://localhost:3000
   - Backend Node.js API: http://localhost:3001
   - Backend Python API: http://localhost:8000
   - PostgreSQL Database: localhost:5432

## Environment Variables

### Database (db)
- `POSTGRES_USER`: postgres
- `POSTGRES_PASSWORD`: postgres
- `POSTGRES_DB`: inkluaticket

### Python Backend (backend-py)
- `POSTGRES_HOST`: db
- `POSTGRES_USER`: postgres
- `POSTGRES_PASSWORD`: postgres
- `POSTGRES_DB`: inkluaticket

### Node.js Backend (backend-node)
- `DATABASE_URL`: Connection string to PostgreSQL
- `STRIPE_SECRET_KEY`: Stripe API secret key

### Frontend (front-end)
- `NEXT_INTERNAL_API_BASE`: Internal API endpoint (http://backend-node:3001)
- `NEXT_PUBLIC_API_BASE`: Public API endpoint (http://localhost:3001)

## Resource Limits

Each service is configured with memory limits:
- Memory limit: 500MB
- Memory reservation: 100MB

## Stopping the Services

```bash
docker-compose down
```

To remove volumes as well:
```bash
docker-compose down -v
```

## License

MIT License - see LICENSE file for details