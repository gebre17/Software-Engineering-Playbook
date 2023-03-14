# Docker & Containerization

Docker packages applications into standardized units called containers containing all system tools, libraries, and runtime dependencies.

## 1. Dockerfile Best Practices
*   **Use Multi-stage Builds:** To reduce final production image size.
*   **Order Layers by Frequency of Change:** Place `COPY package.json` and dependency installers before copying actual source code to maximize build caching.
*   **Use Specific Tags:** Avoid `latest`. Use explicit versions (e.g., `python:3.11-slim`).

```dockerfile
# Build Stage
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Run Stage
FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

## 2. Docker Compose
A tool for defining and running multi-container Docker applications.

```yaml
version: '3.8'

services:
  web:
    build: .
    ports:
      - "8000:8000"
    depends_on:
      - db
  db:
    image: postgres:15
    environment:
      POSTGRES_DB: mydb
      POSTGRES_PASSWORD: mypassword
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```
