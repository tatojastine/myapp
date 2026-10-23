# IPT 102 – Docker Project

A simple full-stack web application built with **React, .NET Web API, PostgreSQL, and Docker Compose**. This project demonstrates how to containerize an application, configure services, manage environment variables, connect containers, and persist database data using Docker volumes.

## Project Overview

The application contains a React frontend, a .NET Web API backend, and a PostgreSQL database. Docker Compose manages the services and their configuration.

### Technologies Used

- **React** – Frontend user interface
- **Vite** – Frontend development and build tool
- **.NET 10 Web API** – Backend API
- **PostgreSQL 16** – Database
- **Docker** – Containerization
- **Docker Compose** – Multi-container application management
- **Git and GitHub** – Version control and project hosting

## Project Structure

```text
myapp/
├── api/
│   ├── Program.cs
│   ├── Dockerfile
│   └── .dockerignore
├── web/
│   ├── src/
│   ├── public/
│   ├── package.json
│   ├── Dockerfile
│   └── .dockerignore
├── .gitignore
├── docker-compose.yml
└── README.md
```

## Features

- React frontend that displays a message from the backend API
- .NET Web API endpoint for retrieving the application message
- Docker images for the frontend and backend
- Docker Compose configuration for running multiple services
- PostgreSQL database container
- Environment variables configured through a `.env` file
- Docker networking between services
- Persistent database storage using a named Docker volume

## Prerequisites

Install the following tools:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/) (for local frontend development)
- [.NET SDK](https://dotnet.microsoft.com/download) (for local backend development)

## How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/tatojastine/myapp.git
cd myapp
```

### 2. Configure Environment Variables

Create a `.env` file in the project root:

```dotenv
APP_MESSAGE=Hello from Docker Compose!
DB_PASSWORD=change_me_123
```

Use a strong password for real deployments. Do not commit your `.env` file to GitHub.

### 3. Start Docker Desktop

Open Docker Desktop and wait until the Docker engine is running.

### 4. Build and Start the Containers

From the project root, run:

```bash
docker compose up --build
```

Docker Compose builds the images and starts the configured services.

### 5. Open the Application

Open the frontend in your browser:

- **Frontend:** http://localhost:3000
- **Backend API:** http://localhost:5000/api/message

The frontend should display the message returned by the backend API.

### 6. Stop the Containers

Press `Ctrl + C` in the terminal, then run:

```bash
docker compose down
```

This stops and removes the containers while preserving the named database volume.

## Useful Docker Commands

Check running containers:

```bash
docker ps
```

View service logs:

```bash
docker compose logs
```

View logs for the API:

```bash
docker compose logs api
```

View logs for the frontend:

```bash
docker compose logs web
```

List Docker images:

```bash
docker images
```

Stop containers and remove the database volume:

```bash
docker compose down -v
```

**Warning:** The `-v` option deletes the named database volume and its stored data.

## Learning Objectives

Through this project, I practiced:

- Creating Dockerfiles for frontend and backend applications
- Building and running Docker images
- Managing multiple services with Docker Compose
- Using environment variables for configuration
- Connecting services through Docker networking
- Running PostgreSQL in a container
- Using Docker volumes to persist database data
- Publishing a project to GitHub using Git

## Author

**Student:** Jastine Nicole Tato
**Course:** IPT 102  
**Project:** Docker Hands-On Activity

## License

This project was created for educational purposes as part of an IPT 102 activity.
