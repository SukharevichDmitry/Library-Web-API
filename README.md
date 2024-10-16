# CRUD Library-Web-API
This project contains three microservices: authservice, bookservice, and libraryservice, along with a PostgreSQL database.

## Microservices

Each microservice is available as a Docker image on [my DockerHub](https://hub.docker.com/r/sukharevichdima/microservicesmanager)

## Commands for AuthService:
### if you use Postman:

### To register:

URL: http://localhost:8083/auth/register 
Method: POST
Body: raw JSON
Data:
{
  "username": "your-username",
  "password": "your-password"
}

### To login:

URL: http://localhost:8083/auth/login 
Method: POST
Bodde: raw JSON
Data:
{
  "username": "your-username",
  "password": "your-password"
}

### if you use cURL:

### To register:
```bash
curl -X POST http://localhost:8083/auth/register -H "Content-Type: application/json" -d '{"username":"your-username", "password":"your-password"}'
```
### To login:
```bash
curl -X POST http://localhost:8083/auth/login -H "Content-Type: application/json" -d '{"username":"your-username", "password":"your-password"}'
```

