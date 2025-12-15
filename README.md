# DevOps API 🚀

<div>
  <img src="https://img.shields.io/badge/-Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/-Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white"/>
  <img src="https://img.shields.io/badge/-Express.js-000000?style=for-the-badge&logo=express&logoColor=white"/>
  <img src="https://img.shields.io/badge/-Neon%20Postgres-2496ED?style=for-the-badge&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/-Drizzle%20ORM-FFDF00?style=for-the-badge&logo=drizzle&logoColor=black"/>
</div>

A **production-ready backend API** built with **Node.js** and **Express.js**, secured with **Arcjet**, backed by **Neon PostgreSQL**, and powered by **Drizzle ORM** and **Zod** for type-safe data handling.  
The project is fully **containerized with Docker** and includes **automated CI/CD pipelines** for linting, testing, and multi-architecture image builds.

---

## 📌 Features

- ⚡ **Node.js + Express.js** REST API
- 🔐 **Arcjet Security** (bot detection, rate limiting, request shielding)
- **Neon PostgreSQL** (serverless Postgres)
- 🧩 **Drizzle ORM** for type-safe SQL queries
- ✅ **Zod** schema validation
- 🐳 **Dockerized** for consistent environments
- 🔄 **Automated CI/CD** with GitHub Actions
- 🧪 **Test environment support** with isolated database
- 📦 **Multi-architecture Docker builds** (amd64 & arm64)
- 📊 Code quality enforced via **ESLint** and **Prettier**

---

## 🏗️ Tech Stack

### Backend

- **[Node.js](https://nodejs.org/)**
- **[Express.js](https://expressjs.com/)**
- **[Drizzle ORM](https://orm.drizzle.team/)**
- **[Zod](https://zod.dev/)**
- **JWT Authentication**

### Database

- **[Neon Postgres](https://neon.com/)**

### Security

- **[Arcjet](https://arcjet.com/)** (bot protection, rate limiting, attack shielding)

### DevOps & Tooling

- **[Docker](https://www.docker.com/)**
- **[Kubernetes](https://kubernetes.io/)**
- **GitHub Actions**
- **ESLint & Prettier**
- **Jest**

---

## 📁 Project Structure

```txt
src/
├── config/          # Environment, database, logger, Arcjet config
├── controllers/     # Request handlers
├── services/        # Auth and CRUD logic
├── models/          # Drizzle ORM schemas
├── routes/          # Express route definitions
├── middleware/      # Auth, security, error handling
├── utils/           # Helpers (cookies, tokens, etc.)
├── validations/     # Zod schemas
├── index.js         # App entry point
```

---

## ⚙️ Environment Variables

Create a .env file in the project root:

```env
# Server Configuration
PORT=3000
NODE_ENV=development
LOG_LEVEL=info

# Database Configuration
DATABASE_URL=

# Arcjet
ARCJET_KEY=
```

Replace the placeholder values with your real credentials. You can get these by signing up at: [**Arcjet**](https://arcjet.com/), [**Neon**](https://neon.com/).

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/muneefrehman/DevOps_API.git
cd acquisitions
```

### 2. Install dependencies

```bash
npm install
```

### 3. Run the app locally

```bash
npm run dev
```

### 4. Test Connectivity

Visit [http://localhost:3000](http://localhost:3000) to verify that the API is working.

---

## 🐳 Running the Project with Docker Compose

This project includes a `docker-compose.dev.yml` file for running the API and its dependencies in a fully containerized environment.

### Prerequisites

Make sure you have the following installed:

- **[Docker](https://www.docker.com/)**
- **Docker Compose** (comes bundled with Docker Desktop)

### 1. Build and start the services

From the project root, run:

```bash
npm run dev:docker
```

This command runs the bash script `dev.sh` that is configured to automate Docker Compose for development.

### 2. Test Connectivity

Visit [http://localhost:3000](http://localhost:3000) to verify that the API is working.

---

## 🔄 CI/CD Workflows

This project includes **three automated GitHub Actions workflows**:

### ✅ Lint & Format

- Runs ESLint and Prettier on every push & PR
- Prevents poorly formatted or invalid code from being merged

### 🧪 Tests

- Runs the full test suite
- Uses a dedicated test environment
- Uploads coverage reports as artifacts
- Generates readable test summaries

### 🐳 Docker Build & Push

- Builds multi-architecture Docker images
- Tags images using branch, commit SHA, timestamps, and latest
- Pushes images to Docker Hub
- Caches layers for faster builds

---

## 🔐 Security

- **Arcjet Shield** protects against common attacks
- **Bot detection** blocks automated traffic
- **Sliding window rate limiting**
- Secure cookies & JWT-based authentication
- Environment-specific configurations

---

## 🧪 Testing

Run the test suite locally:

```bash
npm run test
```

Tests run with:

- NODE_ENV=test
- Isolated test database
- Reduced logging for clarity

---

## 📦 API Example

```env
GET /api/users
Authorization: Bearer <token>
```

```json
{
    "message": "Users retrieved successfully",
    "users": [
        {
            "id": 1,
            "email": "contact@example.com",
            "name": "Admin",
            "role": "admin",
            "created_at": "2025-12-11T07:16:46.486Z",
            "updated_at": "2025-12-11T07:16:46.486Z"
        },
        {
            "id": 2,
            "email": "user@example.com",
            "name": "User",
            "role": "user",
            "created_at": "2025-12-11T07:17:55.687Z",
            "updated_at": "2025-12-11T07:17:55.687Z"
        }
    ],
    "count": 2
}
```

---

## 🧠 Design Principles

- Separation of concerns (controllers, services, models)
- Security-first approach
- Scalable architecture
- Clean, maintainable code
- Production-ready DevOps practices

---

## 🛣️ Roadmap

- Role-based access control (RBAC)
- API versioning
- OpenAPI / Swagger documentation
- Kubernetes deployment manifests
- E2E test suite
- Rate-limit dashboards & metrics
