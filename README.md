# PostgreSQL Database with pgAdmin Setup

This project sets up a PostgreSQL database with pgAdmin using Docker Compose.

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed on your machine
- [Git](https://git-scm.com/downloads) (optional)

## Setup Instructions

1. Clone or download this repository:
   ```bash
   git clone git@github.com:sagarthakore/postgresql-database.git
   cd postgresql-database
   ```

2. Create a `.env` file in the project root with the following content:
   ```env
   POSTGRES_USER=admin
   POSTGRES_PASSWORD=adminpassword
   POSTGRES_DB=mydatabase
   PGADMIN_DEFAULT_EMAIL=admin@example.com
   PGADMIN_DEFAULT_PASSWORD=pgadminpassword
   ```
   > ⚠️ Make sure to change these default values for production use

3. Start the containers:
   ```bash
   docker compose up -d
   ```

4. Access pgAdmin:
   - Open your browser and navigate to `http://localhost:8080`
   - Login using the credentials set in your `.env` file:
     - Email: `PGADMIN_DEFAULT_EMAIL`
     - Password: `PGADMIN_DEFAULT_PASSWORD`

5. Connect to PostgreSQL in pgAdmin:
   - Right click on 'Servers' → 'Register' → 'Server'
   - In the General tab, give your connection a name
   - In the Connection tab, enter:
     - Host: `db` (service name from docker-compose)
     - Port: `5432`
     - Database: `mydatabase` (or your `POSTGRES_DB` value)
     - Username: `admin` (or your `POSTGRES_USER` value)
     - Password: Your `POSTGRES_PASSWORD` value

## Connection Details

- PostgreSQL Database:
  - Host: `localhost`
  - Port: `5432`
  - Database: `mydatabase` (or your custom name)
  - Username: `admin` (or your custom username)
  - Password: as set in `.env`

- pgAdmin:
  - URL: `http://localhost:8080`
  - Default email: as set in `.env`
  - Default password: as set in `.env`

## Stopping the Services

To stop the containers:
```bash
docker compose down
```

To stop and remove all data (volumes):
```bash
docker compose down -v
```

## Data Persistence

Data is persisted in local folders:
- `postgres_data`: PostgreSQL data
- `pgadmin_data`: pgAdmin configurations

These volumes persist even after containers are removed, unless you explicitly remove them.