To enter data use "routes.txt" file in root of server folder

hosted at: https://rail-routes-client-8dn2pbhih.vercel.app

# Full-Stack Application Deployment

This repository contains a full-stack application composed of a **Next.js** frontend and a **NestJS** backend. Both services are containerized using Docker and orchestrated using Docker Compose for simple, one-command deployment [web:3][web:5].

## 📁 Project Structure

For this setup to work correctly, ensure your project is structured as follows [web:9][web:12]:

.
├── client/ # Contains the Next.js Frontend code
│ ├── Dockerfile # Dockerfile for the frontend service
│ └── nginx.conf # NGINX configuration for serving the build
├── server/ # Contains the NestJS Backend code
│ └── Dockerfile # Dockerfile for the backend service
├── docker-compose.yml # Orchestrates both services
└── README.md

## ⚙️ Prerequisites

You must have Docker and Docker Compose installed on your system [web:17]:

- **Docker**: [Installation Guide](https://docs.docker.com/get-docker/)
- **Docker Compose**: Typically included with Docker Desktop

## ▶️ How to Run the Application

Follow these steps to build and start both the frontend and backend services [web:8][web:14]:

### 1. Build and Run the Containers

Navigate to the root directory of your project (where `docker-compose.yml` is located) and run the following command:

docker compose up --build -d

### 2. Verify Status

You can check the status of your running containers with [web:20]:

docker compose ps

You should see both `nest_backend` and `nsxt_frontend` containers in a healthy/running state [web:14].

### 3. Access the Application

Once the containers are running:

| Service                | Access URL            | Port                          |
| ---------------------- | --------------------- | ----------------------------- |
| **Frontend (Web App)** | http://localhost:3000 | Mapped to container port 80   |
| **Backend (API)**      | http://localhost:3001 | Mapped to container port 3001 |

The frontend service (`nsxt-frontend`) is automatically configured to communicate with the backend service (`nest-backend`) internally using the URL `http://backend:3001` as defined in `docker-compose.yml` [web:14].

### 4. Stopping and Cleaning Up

To stop the running containers [web:20]:

docker compose stop

To stop and remove all containers, networks, and volumes associated with this project (clean shutdown) [web:17]:

docker compose down -v

## 🛠️ Development

This application follows modern full-stack development practices with proper separation of concerns between frontend and backend services [web:15][memory:1]. The containerized approach ensures consistent deployment across different environments [web:17].

## 📚 Tech Stack

- **Frontend**: Next.js (React Framework)
- **Backend**: NestJS (Node.js Framework)
- **Containerization**: Docker & Docker Compose
- **Web Server**: NGINX (for production builds)

## 🔧 Configuration

Both services are configured to work together seamlessly through Docker Compose networking, allowing the frontend to communicate with the backend using service names defined in the compose file [web:14][web:8].
