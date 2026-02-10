# Question 1: Library-Book-Management-API

## Project Description
A RESTful API for library book management built with Spring Boot.

## Project Structure
```
src/main/java/com/library/question1libraryapi/
├── controller/
│   └── library/
│       └── BookController.java
├── model/
│   └── library/
│       └── Book.java
└── Question1LibraryApiApplication.java
```


1. The application will start on `http://localhost:8080`

## API Endpoints

### 1. Get All Books
- **URL:** `/api/books`
- **Method:** `GET`
- **Status Code:** `200 OK`
- **Description:** Retrieves all books in the library

**Sample Response:**
```json
[
  {
    "id": 1,
    "title": "Clean Code",
    "author": "Robert Martin",
    "isbn": "978-0132350884",
    "publicationYear": 2008
  },
  {
    "id": 2,
    "title": "Effective Java",
    "author": "Joshua Bloch",
    "isbn": "978-0134685991",
    "publicationYear": 2017
  }
]
```

---

### 2. Get Book by ID
- **URL:** `/api/books/{id}`
- **Method:** `GET`
- **Status Codes:** 
  - `200 OK` - Book found
  - `404 NOT FOUND` - Book not found

**Sample Request:**
```
GET http://localhost:8080/api/books/1
```

**Sample Response (200 OK):**
```json
{
  "id": 1,
  "title": "Clean Code",
  "author": "Robert Martin",
  "isbn": "978-0132350884",
  "publicationYear": 2008
}
```

---

### 3. Search Books by Title
- **URL:** `/api/books/search?title={title}`
- **Method:** `GET`
- **Status Code:** `200 OK`
- **Description:** Searches for books by title (case-insensitive, partial match)

**Sample Request:**
```
GET http://localhost:8080/api/books/search?title=clean
```

**Sample Response:**
```json
[
  {
    "id": 1,
    "title": "Clean Code",
    "author": "Robert Martin",
    "isbn": "978-0132350884",
    "publicationYear": 2008
  }
]
```

---

### 4. Add New Book
- **URL:** `/api/books`
- **Method:** `POST`
- **Status Code:** `201 CREATED`
- **Content-Type:** `application/json`

**Sample Request:**
```json
POST http://localhost:8080/api/books
Content-Type: application/json

{
  "title": "Spring Boot in Action",
  "author": "Craig Walls",
  "isbn": "978-1617292545",
  "publicationYear": 2016
}
```

**Sample Response (201 CREATED):**
```json
{
  "id": 4,
  "title": "Spring Boot in Action",
  "author": "Craig Walls",
  "isbn": "978-1617292545",
  "publicationYear": 2016
}
```

---

### 5. Delete Book
- **URL:** `/api/books/{id}`
- **Method:** `DELETE`
- **Status Codes:**
  - `204 NO CONTENT` - Successfully deleted
  - `404 NOT FOUND` - Book not found

**Sample Request:**
```
DELETE http://localhost:8080/api/books/3
```

**Sample Response (204 NO CONTENT):**
```
Empty body
```

---

## Sample Book Data

The application initializes with 3 sample books:

1. **Clean Code** by Robert Martin (2008) - ISBN: 978-0132350884
2. **Effective Java** by Joshua Bloch (2017) - ISBN: 978-0134685991
3. **Design Patterns** by Gang of Four (1994) - ISBN: 978-0201633612

---

## Testing the API

### Using Browser
For GET requests, you can use your browser:
- `http://localhost:8080/api/books`
- `http://localhost:8080/api/books/1`
- `http://localhost:8080/api/books/search?title=clean`

### Using Postman
Test all 5 endpoints as documented above.

### Using cURL

**Get All Books:**
```bash
 http://localhost:8080/api/books
```

**Get Book by ID:**
```bash
 http://localhost:8080/api/books/1
```

**Search by Title:**
```bash
 "http://localhost:8080/api/books/search?title=clean"
```

**Add New Book:**
```bash
 POST http://localhost:8080/api/books \
  -H "Content-Type: application/json" \
  -d '{"title":"Spring Boot","author":"Craig Walls","isbn":"978-1617292545","publicationYear":2016}'
```

**Delete Book:**
```bash
DELETE http://localhost:8080/api/books/3
```

---

## HTTP Status Codes Used

| Code | Meaning | Used For |
|------|---------|----------|
| **200 OK** | Success | GET requests |
| **201 CREATED** | Resource created | POST (add book) |
| **204 NO CONTENT** | Success, no body | DELETE (remove book) |
| **404 NOT FOUND** | Resource not found | GET/DELETE when book doesn't exist |

---

## Key Concepts

### REST API Basics
- **GET** - Retrieve data
- **POST** - Create new data
- **DELETE** - Remove data

### Path Variables
- `/api/books/{id}` - `{id}` is extracted from URL
- Example: `/api/books/1` → `id = 1`

### Query Parameters
- `/api/books/search?title=clean`
- `?` separates URL from parameters
- `title=clean` is the query parameter

### JSON Format
- All data is sent/received as JSON
- Easy for both humans and computers to read

---
SCREEN SHOTS FOR OUT PUTS
<img width="1267" height="915" alt="Screenshot 2026-02-04 204213" src="https://github.com/user-attachments/assets/ccb7d356-df15-47c9-b8ce-8f5717454c0f" />
---
<img width="1275" height="899" alt="Screenshot 2026-02-04 214103" src="https://github.com/user-attachments/assets/7a20e9cf-eda2-4e77-904e-ca819f6a6bcf" />
---
<img width="1285" height="900" alt="Screenshot 2026-02-04 214244" src="https://github.com/user-attachments/assets/78daeaaa-ad70-4bc5-b5d0-c59bb4db3f31" />
---
<img width="1296" height="891" alt="Screenshot 2026-02-04 214624" src="https://github.com/user-attachments/assets/538171cb-1d76-4ebb-9b8d-aa2812af5578" />
---


## Author
SHEDRICK BUCAGU ELISA  
26939

## Date
February 5, 2026
