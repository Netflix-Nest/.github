# Netflix Clone — Microservices Architecture

Welcome to the **Netflix Clone Project**, built with modern **Microservice Architecture** using **NestJS**, **Next.js**, **React Native**, **PostgreSQL**, **FFmpeg**, and **Message Broker** (RabbitMQ or Redis).

## About

This is an end-to-end learning project to demonstrate how to build a production-like video streaming system similar to Netflix, with these goals:
- Modular microservices.
- Asynchronous video transcoding (HLS/DASH) with FFmpeg.
- Authentication & Authorization with JWT.
- User upload, watch, comment, watchlist, notifications.
- Multi-client: Web + Mobile App (React Native).
- Ready for logging, monitoring, and scaling.

## Tech Stack

| Layer | Tech |
|-------|------|
| Backend | NestJS |
| Frontend | Next.js |
| Mobile | React Native |
| Database | PostgreSQL |
| Message Broker | RabbitMQ / Redis |
| Media Processing | FFmpeg |
| Object Storage | Local Disk / Minio / S3 |
| Gateway | API Gateway with Auth Guard |
| Logging/Monitoring | ELK, Prometheus (optional) |
| Deployment | Docker Compose, CI/CD |

## Project Structure

/netflix-clone-org
 ├── .github/
 ├── api-gateway/
 ├── auth-service/
 ├── video-service/
 ├── comment-service/
 ├── watchlist-service/
 ├── notification-service/
 ├── transcoding-worker/
 ├── mobile-app/ (React Native)
 ├── web-client/ (Next.js)
 ├── infra/ (docker-compose.yml, k8s, scripts)
 ├── docs/ (designs, schema, diagrams)
 ├── README.md

## System Overview

- **API Gateway:** Entry point for all clients. Handles JWT auth, routes requests.
- **Auth Service:** Register, login, refresh token, RBAC.
- **Video Service:** Upload raw video, save metadata, push transcoding job.
- **Transcoding Worker:** Consume jobs, run FFmpeg, output HLS chunks, update status.
- **Message Broker:** Queue jobs (RabbitMQ or Redis Streams).
- **Object Storage:** Store video chunks (local folder, Minio, or cloud S3).
- **Comment Service:** CRUD comments linked to video & user.
- **Watchlist Service:** User watchlist CRUD.
- **Notification Service:** Push email or FCM notifications.
- **Log Service:** Collect logs, metrics.

## Key Features

- Upload & Stream: Upload raw video → transcoding → serve HLS chunks.
- Metadata: Store info in PostgreSQL.
- Comments: Users can comment under videos.
- Watchlist: Save favorite shows.
- Notifications: Get notified when new videos are ready.
- Queue-based pipeline: Non-blocking transcoding flow.
- JWT Auth: Secure endpoints.
- Mobile Ready: Watch videos on mobile.
- Infrastructure as Code: Docker Compose setup.

## Getting Started

# Clone this organization

```
git clone https://github.com/Netflix-Nest/Netflix-Server.git

git clone https://github.com/Netflix-Nest/Netflix-Client.git

git clone https://github.com/Netflix-Nest/Netflix-Mobile.git
```

# Start local development

```
docker-compose up --build
```

# Visit Gateway

```
http://localhost:3000
```
## Docs

- System Architecture: docs/system-architecture.pdf
- Data Flow Diagram: docs/data-flow.pdf
- API Docs: Swagger / Postman collection per service
- Dev Guides: FFmpeg scripts, transcoding examples

## 🗒️ Sprint Backlog

| Sprint | Deliverables |
|--------|---------------|
| Sprint 1 | Auth, Upload, Video Service, Transcoding Worker, Streaming |
| Sprint 2 | Comments, Watchlist, Notifications |
| Sprint 3 | Mobile App, Polished UI/UX, Logging/Monitoring, Deploy Scripts |

## Credits

This project is for educational purposes, inspired by Netflix but not for commercial use.

Built with ❤️ by Cao Tri Ngoc.

## License

MIT

Happy Streaming! 🌅
