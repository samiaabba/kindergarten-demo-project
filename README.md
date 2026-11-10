# Kindergarten — Nginx Reverse Proxy

I used my teacher’s Docker phase as the starting point and added Nginx
to route browser requests to the frontend and backend services.

## General Steps

1. Create an Nginx configuration with routes for the frontend and APIs.
2. Add Nginx to Docker Compose and mount its configuration file.
3. Point the frontend API URLs to the proxy routes.
4. Remove the frontend’s host port mapping.
5. Rebuild the containers and test the application.

## Port Issues Fixed

- Port 80 was occupied by Ubuntu Nginx, so I used `8080:80`.
- Port 3000 was occupied, so I removed the frontend’s `3000:80` mapping.
  Nginx connects internally to `frontend:80`.

## Run

Configure the environment files, then run:

```bash
docker compose -f docker-compose.yml up -d --build
```

Open **http://localhost:8080**.


