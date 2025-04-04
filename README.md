# 🐘 PostgreSQL Database with pgAdmin Setup

Welcome to the most exciting database setup you'll do today! (Okay, maybe the only database setup you'll do today... but let's make it fun!) 🎉

## 🎯 Prerequisites

Before we dive into the world of databases, make sure you have:
- 🐳 [Docker Desktop](https://www.docker.com/products/docker-desktop/) (Because who doesn't love containers?)
- 🌿 [Git](https://git-scm.com/downloads) (optional, but hey, you're cool if you use it!)

## 🚀 Setup Instructions

1. First, let's get this party started:
   ```bash
   git clone git@github.com:sagarthakore/postgresql-database.git
   cd postgresql-database   # Welcome to your new home! 🏠
   ```

2. Create a magical `.env` file in the project root:
   ```env
   POSTGRES_USER=admin
   POSTGRES_PASSWORD=adminpassword
   POSTGRES_DB=mydatabase
   PGADMIN_DEFAULT_EMAIL=admin@example.com
   PGADMIN_DEFAULT_PASSWORD=pgadminpassword
   ```
   > ⚠️ Pro tip: Using these default passwords in production is like using "password123" - Don't do it! 🙈

3. Launch the containers (Warning: May cause extreme database satisfaction):
   ```bash
   docker compose up -d   # The -d stands for "delightful" (not really, but wouldn't that be fun?)
   ```

4. Time to meet pgAdmin 🤝:
   - Open your favorite browser (I won't judge) and go to `http://localhost:8080`
   - Login with your super-secret credentials from the `.env` file
   - If you forgot them already, scroll up! I won't tell anyone 😉

5. Connect to PostgreSQL in pgAdmin (The moment of truth! 🥁):
   - Right click 'Servers' → 'Register' → 'Server' (Yes, it's like a Russian doll of menus)
   - Fill in the details:
     - Host: `db` (Keep it simple!)
     - Port: `5432` (The classic)
     - Database: `mydatabase` (Or whatever creative name you chose)
     - Username: `admin` (Original, right?)
     - Password: The one you definitely didn't forget from earlier 🔑

## 🔌 Connection Details

- PostgreSQL Database (Your new best friend):
  - Host: `localhost` (As local as your coffee ☕)
  - Port: `5432`
  - The rest: You know the drill!

- pgAdmin (Your database's window to the world 🌍):
  - URL: `http://localhost:8080`
  - Login: Check that `.env` file one more time!

## 🛑 Stopping the Services

When it's time to say goodbye:
```bash
docker compose down   # See you later, allocator! 👋
```

Want to start fresh? Nuclear option incoming:
```bash
docker compose down -v   # Goodbye data, my old friend... 💥
```

## 💾 Data Persistence

Your data is safely stored in:
- `postgres_data`: Where the PostgreSQL magic happens ✨
- `pgadmin_data`: pgAdmin's cozy home 🏡

These survive container restarts because data, like diamonds, is forever! 💎

Happy databasing! May your queries be fast and your connections never time out! 🚀