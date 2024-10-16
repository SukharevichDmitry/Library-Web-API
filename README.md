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

### If you use cURL:
* #### To get all books:
```bash
curl -X GET http://localhost:8081/books
```
* #### To get book by id:
```bash
curl -X GET http://localhost:8081/books/{id}
```
* #### To get book by isbn:
```bash
curl -X GET http://localhost:8081/books/isbn/{isbn}
```

* #### To create book
```bash
curl -X POST http://localhost:8081/books -H "Content-Type: application/json" -d '{"title":"New Book Title", "author":"Author Name", "isbn":"1234567890123", "publishedDate":"2024-01-01"}'
```

* #### To update book
```bash
curl -X PUT http://localhost:8081/books/{id} -H "Content-Type: application/json" -d '{"title":"Updated Book Title", "author":"Updated Author Name", "isbn":"9876543210987", "publishedDate":"2025-01-01"}'
```

* #### To delete book:
```bash
curl -X DELETE http://localhost:8081/books/{id}
```

### If you use JavaScript(Fetch API):

* #### To get all books:
```JavaScript

```
* ####
```JavaScript
fetch('http://localhost:8081/books', {
    method: 'GET',
    headers: {
        'Content-Type': 'application/json'
    }
})
.then(response => response.json())
.then(data => console.log('Books:', data))
.catch(error => console.error('Error:', error));
```
* ####
```JavaScript

```
* #### To get book by id:
```JavaScript
fetch('http://localhost:8081/books/{id}', { 
    method: 'GET',
    headers: {
        'Content-Type': 'application/json'
    }
})
.then(response => response.json())
.then(data => console.log('Book by ID:', data))
.catch(error => console.error('Error:', error));
```
* #### To get book by isbn:
```JavaScript
To get book by isbn:

fetch('http://localhost:8081/books/isbn/{isbn}', { 
    method: 'GET',
    headers: {
        'Content-Type': 'application/json'
    }
})
.then(response => response.json())
.then(data => console.log('Book by ISBN:', data))
.catch(error => console.error('Error:', error));
```
* #### To create book:
```JavaScript
fetch('http://localhost:8081/books', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
   	title : 'your_title',
   	author : 'your_author',
   	isbn : 'your_isbn',
   	genre : 'your_genre',
   	description : 'your_description'
    })
})
.then(response => response.json())
.then(data => console.log('Created Book:', data))
.catch(error => console.error('Error:', error));
```
* #### To update book:
```JavaScript
To update book:

fetch('http://localhost:8081/books/{id}', { 
    method: 'PUT',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
   	title : 'your_title',
   	author : 'your_author',
   	isbn : 'your_isbn',
   	genre : 'your_genre',
   	description : 'your_description'
    })
})
.then(response => response.json())
.then(data => console.log('Updated Book:', data))
.catch(error => console.error('Error:', error));
```
* #### To delete book:
```JavaScript
To delete book:

fetch('http://localhost:8081/books/{id}', {
    method: 'DELETE',
    headers: {
        'Content-Type': 'application/json'
    }
})
.then(response => {
    if (response.ok) {
        console.log('Book deleted');
    } else {
        console.error('Error deleting book');
    }
})
.catch(error => console.error('Error:', error));
```
