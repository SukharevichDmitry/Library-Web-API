# CRUD Library-Web-API
This project contains three microservices: authservice, bookservice, and libraryservice, along with a PostgreSQL database.

## Microservices

Each microservice is available as a Docker image on [my DockerHub](https://hub.docker.com/r/sukharevichdima/microservicesmanager)

## Commands for AuthService:
### If you use [Postman](https://www.postman.com/downloads/):

* #### to register:
```HTML
URL: http://localhost:8083/auth/register
Method: POST
Body: raw JSON
Data:
{
  "username": "your-username",
  "password": "your-password"
}
```
* #### to login:
```HTML
URL: http://localhost:8083/auth/login 
Method: POST
Bodde: raw JSON
Data:
{
  "username": "your-username",
  "password": "your-password"
}
```

### If you use cURL:

* #### to register:
```bash
curl -X POST http://localhost:8083/auth/register -H "Content-Type: application/json" -d '{"username":"your-username", "password":"your-password"}'
```
* #### to login:
```bash
curl -X POST http://localhost:8083/auth/login -H "Content-Type: application/json" -d '{"username":"your-username", "password":"your-password"}'
```


### If you use JavaScript(Fetch API):

* #### to register:
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

* #### to login:
```JavaScript
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
```

## Commands for BookService:

### If you use Postman:

* #### to get all books:
```HTML
URL: http://localhost:8081/books
Method: GET
Body: raw JSON
Data: null
Authorization: Auth Type - Bearer Token, Token - <your_token>
```

* #### to get book by id:
```HTML
URL: http://localhost:8081/books/{id}
Method: GET
Body: raw JSON
Data: null
Authorization: Auth Type - Bearer Token, Token - <your_token>
```
* #### to get book by isbn:
```HTML
URL: http://localhost:8081/books/isbn/{isbn}
Method: GET
Body: raw JSON
Data: null
Authorization: Auth Type - Bearer Token, Token - <your_token>
```
* #### to create book:
```HTML
URL: http://localhost:8081/books
Method: POST
Body: raw JSON
Data: 
{
   "title" : "your_title",
   "author" : "your_author",
   "isbn" : "your_isbn",
   "genre" : "your_genre",
   "description" : "your_description"
}
Authorization: Auth Type - Bearer Token, Token - <your_token>
```
* #### to update book:
```HTML
URL: http://localhost:8081/books/{id}
Method: PUT
Body: raw JSON
Data:
{
   "title" : "your_title",
   "author" : "your_author",
   "isbn" : "your_isbn",
   "genre" : "your_genre",
   "description" : "your_description"
}
Authorization: Auth Type - Bearer Token, Token - <your_token>
```
* #### to delete book:
```HTML
URL: http://localhost:8081/books/{id}
Method: DELETE
Body: raw JSON
Data: null
Authorization: Auth Type - Bearer Token, Token - <your_token>
```
