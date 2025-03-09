#  API Deployment Guide
## 📌 Overview
This project provides a Django REST API with PostgreSQL as the database. The service is containerized using Podman Compose for deployment.

## 📌 Prerequisites
Ensure you have the following installed:

- Podman (>= 4.x)
- Python (>= 3.8) (if running locally)
- PostgreSQL (>= 13)

## 📌 Configuration
Create a .env file in the root directory and configure your environment:
```
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=db  # The hostname for the PostgreSQL service in Podman
DB_PORT=5432
```


## 📌 Deployment Setps
```sh
$ podman-compose up --build -d
```
