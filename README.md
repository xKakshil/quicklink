# 🚀 QuickLink

<p align="center">
  <a href="https://quicklinkmhp8.onrender.com/health">
    <img src="https://img.shields.io/badge/status-live-brightgreen" alt="Live">
  </a>
  <img src="https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript" alt="TypeScript">
  <img src="https://img.shields.io/badge/Express-Backend-black?logo=express" alt="Express">
  <img src="https://img.shields.io/badge/MongoDB-Database-green?logo=mongodb" alt="MongoDB">
  <img src="https://img.shields.io/badge/Redis-Cache-red?logo=redis" alt="Redis">
  <img src="https://img.shields.io/badge/Deploy-Render-purple" alt="Render">
  <a href="https://opensource.org/licenses/ISC">
    <img src="https://img.shields.io/badge/License-ISC-blue" alt="ISC License">
  </a>
</p>

A production-ready URL shortening service built with **TypeScript**, **Express**, **MongoDB Atlas**, and **Redis Cloud**. QuickLink follows a clean layered architecture with dependency injection using **tsyringe**, cache-first lookups, and RESTful APIs for high-performance URL shortening.

## 🌐 Live Demo

**Application:** https://quicklinkmhp8.onrender.com

**Health Check:** https://quicklinkmhp8.onrender.com/health

---

# ✨ Features

- Generate unique 5-character short URLs
- Redis cache-first architecture for faster redirects
- MongoDB Atlas persistent storage
- Dependency Injection using tsyringe
- Input validation using Zod
- Health monitoring endpoint
- Landing page with URL shortening form
- RESTful API architecture
- Production deployment on Render

---

# 🛠 Tech Stack

| Category | Technology |
|----------|------------|
| Language | TypeScript |
| Runtime | Node.js |
| Framework | Express.js |
| Database | MongoDB Atlas |
| Cache | Redis Cloud |
| Validation | Zod |
| Dependency Injection | tsyringe |
| Deployment | Render |

---

# 📁 Project Structure

```
Controllers/
Services/
Repositories/
Interfaces/
Routes/
config/
container.js
index.ts
```

---

# 🚀 API Endpoints

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | / | Landing page |
| GET | /health | Health check |
| POST | / | Create short URL |
| GET | /:shortCode | Redirect to original URL |

---

## Create Short URL

### Request

```http
POST /
Content-Type: application/json
```

```json
{
  "longUrl": "https://example.com"
}
```

### Response

```json
{
  "shortUrl": "aB3xZ"
}
```

---

# 📊 Request Flow

```
             Client
                │
                ▼
          Express Router
                │
                ▼
          URL Controller
                │
                ▼
          URL Service
                │
      ┌─────────┴─────────┐
      ▼                   ▼
    Redis             MongoDB
(Cache Hit)       (Cache Miss)
      │                   │
      └─────────┬─────────┘
                ▼
             Response
```

---

# ⚙️ Local Setup

## Clone Repository

```bash
git clone https://github.com/xKakshil/quicklink.git

cd quicklink

npm install
```

---

## Configure Environment

Create a `.env` file.

```env
PORT=3001

MONGO_URI=your_mongodb_connection_string

DB_NAME=quicklink

REDIS_HOST=your_redis_host
REDIS_PORT=your_redis_port
REDIS_USERNAME=default
REDIS_PASSWORD=your_redis_password
```

---

## Run Locally

Development

```bash
npm run dev
```

Production

```bash
npm run build
npm start
```

Server runs on

```
http://localhost:3001
```

---

# 🧪 API Testing

Health Check

```bash
curl https://quicklinkmhp8.onrender.com/health
```

Create Short URL

```bash
curl -X POST https://quicklinkmhp8.onrender.com \
-H "Content-Type: application/json" \
-d '{"longUrl":"https://example.com"}'
```

---

# 📄 License

Licensed under the ISC License.

---

# 👨‍💻 Author

**Kakshil Kumar**

GitHub: https://github.com/xKakshil

LinkedIn: https://linkedin.com/in/kakshil