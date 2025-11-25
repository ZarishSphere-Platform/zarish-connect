# Zarish-Connect (API Gateway)

API Gateway for ZarishSphere Platform, routing requests to microservices.

## Features

- Reverse proxy to backend services
- CORS support
- Health check endpoint
- Service discovery

## Routes

- `/api/fin/*` → zarish-fin (port 8081)
- `/api/hra/*` → zarish-hra (port 8082)
- `/api/his/*` → zarish-his (port 8083)
- `/health` → Gateway health check

## Running

```bash
go run cmd/server/main.go
```

Gateway runs on port **8080**.

## Example Requests

```bash
# Create a patient via gateway
curl -X POST http://localhost:8080/api/his/api/v1/patients \
  -H "Content-Type: application/json" \
  -d '{"first_name":"John","last_name":"Doe","mrn":"MRN001"}'

# List employees via gateway
curl http://localhost:8080/api/hra/api/v1/employees
```

## Technology Stack

- Go 1.21+
- Gin Web Framework
- HTTP Reverse Proxy
