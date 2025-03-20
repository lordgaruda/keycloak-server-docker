# Keycloak & PostgreSQL Docker Setup

This repository contains a Docker Compose configuration for setting up Keycloak with PostgreSQL as the database.

## 🛠 Setup & Configuration

### Prerequisites

- **Docker** (version 20+ recommended)
- **Docker Compose** (version 3.8+)

### 1️⃣ **PostgreSQL (Database)**
- Uses the official **PostgreSQL 15** image.
- Stores Keycloak user data.
- Credentials:
  - **Database:** `keycloak`
  - **User:** `keycloak`
  - **Password:** `password`
- Stores data in a persistent volume `postgres_data`.
- Includes a health check to ensure PostgreSQL is ready before Keycloak starts.

### 2️⃣ **Keycloak (Identity & Access Management)**
- Uses the official **Keycloak (latest) image**.
- Configured to use **PostgreSQL** as its database.
- Exposed on port **8888** (accessible at `http://localhost:8888`).
- Admin credentials:
  - **Username:** `admin`
  - **Password:** `admin123`
- TLS certificates can be placed in the `certs/` directory.

## 🚀 Running the Setup

1. Clone the repository:
   ```sh
   git clone https://github.com/lordgaruda/keycloak-server-docker
   cd keycloak-server-docker
   ```
   
2. Start the containers:
```
docker-compose up -d
```

3. Check if the containers are running:
```
docker ps
```
Access Keycloak at:
http://localhost:8888
Login with admin / admin123.
