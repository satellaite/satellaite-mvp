# Project Setup and Usage

This project is a multi-service application including two PostgreSQL databases, an API service, and a UI service. All services are orchestrated using Docker Compose.

## Prerequisites

- **Docker** (latest version recommended)
- **Docker Compose** (latest version recommended)

## Environment Configuration

Before running the project, you must configure environment variables:

1. Copy the provided `.env.example` file to `.env` in the project root:
   ```bash
   cp .env.example .env
   ```
2. Edit the `.env` file and provide values for the following variables:

   - `OPENAI_API_KEY`: Your OpenAI API key (required for sat-ui)
   - `DEMO_DB_USER`: Username for the demo-db PostgreSQL instance
   - `DEMO_DB_PASSWORD`: Password for the demo-db PostgreSQL instance
   - `SYSTEM_DB_USER`: Username for the system-db PostgreSQL instance
   - `SYSTEM_DB_PASSWORD`: Password for the system-db PostgreSQL instance

## Running the Project

Start all services using Docker Compose:

```bash
docker-compose up
```

This will start the following services:
- **demo-db**: PostgreSQL database for demo data (port 5432)
- **system-db**: PostgreSQL database for system data (port 5444)
- **sat-api**: Backend API service (ports 8070, 8090)
- **sat-ui**: Frontend UI service (port 3000)

### Accessing the Services

- **UI**: [http://localhost:3000](http://localhost:3000)
- **API**: [http://localhost:8070](http://localhost:8070) (main API)
- **API (internal)**: [http://localhost:8090](http://localhost:8090)
- **Demo DB**: `localhost:5432` (PostgreSQL)
- **System DB**: `localhost:5444` (PostgreSQL)


## Notes

- All services are open by default; no authentication is required for initial access.
- Docker Compose manages service dependencies, but initial startup may require a UI restart as described above.
- For best results, use the latest versions of Docker and Docker Compose.
