# CRUD Library-Web-API
This project contains three microservices: authservice, bookservice, and libraryservice, along with a PostgreSQL database.

## Microservices

Each microservice is available as a Docker image on [my DockerHub](https://hub.docker.com/r/sukharevichdima/microservicesmanager)

## Commands for AuthService:
#### If you use Postman:

#### to register:

URL: http://localhost:8083/auth/register

Method: POST

Body: raw JSON

Data:
```HTML
{

  "username": "your-username",
  
  "password": "your-password"
  
}
```
#### to login:

URL: http://localhost:8083/auth/login 
Method: POST
Bodde: raw JSON
Data:
```bash
{
  "username": "your-username",
  "password": "your-password"
}
```

### If you use cURL:

#### to register:
```bash
curl -X POST http://localhost:8083/auth/register -H "Content-Type: application/json" -d '{"username":"your-username", "password":"your-password"}'
```
#### to login:
```bash
curl -X POST http://localhost:8083/auth/login -H "Content-Type: application/json" -d '{"username":"your-username", "password":"your-password"}'
```


### If you use JavaScript(Fetch API):

#### To register:
```JavaScript 
fetch('http://localhost:8083/auth/register', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        username: 'new-username',
        password: 'new-password'
    })
})
.then(response => {
    if (response.ok) {
        console.log('Registration successful');
    } else {
        console.error('Registration failed');
    }
})
.catch(error => console.error('Error:', error));
```

#### To login:

fetch('http://localhost:8083/auth/login', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        username: 'your-username',
        password: 'your-password'
    })
})
.then(response => response.json())
.then(data => console.log('Success:', data))
.catch(error => console.error('Error:', error));
