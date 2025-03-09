#  API Deployment Guide
### 📌 Overview
This project provides a **Django REST API** with **PostgreSQL** as the database. The service is containerized using Podman Compose for deployment.

### 📌 Prerequisites
Ensure you have the following installed:

- Podman (>= 4.x)
- Python (>= 3.8) (if running locally)
- PostgreSQL (>= 13)

### 📌 Configuration
Create a .env file in the root directory and configure your environment:
```
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=db  # The hostname for the PostgreSQL service in Podman
DB_PORT=5432
```


### 📌 Deployment Setps
1. Clone the repository
```sh
$ git clone https://github.com/your-repo/your-api.git
```
2. Build and start services
```sh
$ podman-compose up --build -d
```
Ensure that both the web (Django API) and db (PostgreSQL) services are running.

### 📌 API Documentation
Once the service is running, you can access the interactive API documentation: 👉 http://127.0.0.1:8000/swagger/

### 📌 Using the API
1. Create a new user
```sh
$ curl -X POST "http://127.0.0.1:8000/api/users/" -H "Content-Type: application/json" -d '{"name": "Alice", "email": "alice@example.com"}'
```
2. Update the user
```sh
$ curl -X PUT "http://127.0.0.1:8000/api/users/1/" -H "Content-Type: application/json" -d '{"name": "Alice Updated"}'
```
3. Delete the user
```sh
$ curl -X DELETE "http://127.0.0.1:8000/api/users/1/"
```
4. 2. Get a List of Users
```sh
$ curl -X GET "http://127.0.0.1:8000/api/users/"
```
