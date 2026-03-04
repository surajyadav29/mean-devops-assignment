# MEAN Stack CRUD Application

## Project Overview

This project is a Dockerized MEAN (MongoDB, Express, Angular, Node.js) stack CRUD application.  
It consists of an Angular frontend, a Node.js/Express backend API, MongoDB database, and Nginx as a reverse proxy.  
The entire application is containerized using Docker and managed with Docker Compose.

------------------------------------------------------------

## Technologies Used

Frontend:
- Angular

Backend:
- Node.js
- Express

Database:
- MongoDB

Infrastructure:
- Docker
- Docker Compose
- Nginx

CI/CD:
- GitHub Actions (or configured CI pipeline)

------------------------------------------------------------

## Project Structure

backend/        -> Express API  
frontend/       -> Angular application  
nginx/          -> Nginx configuration  
docker-compose.yml  
README.md  

------------------------------------------------------------

## Prerequisites

Make sure the following are installed:

- Git
- Docker
- Docker Compose

Check versions:

docker --version
docker-compose --version

------------------------------------------------------------

## Running the Application Locally (Docker)

1. Clone the repository:

git clone <your-repository-url>
cd <project-folder>

2. Build and start containers:

docker-compose up --build -d

3. Verify containers are running:

docker ps

4. Access the application:

Frontend:
http://localhost

Backend API:
http://localhost/api/tutorials

5. Stop the application:

docker-compose down

------------------------------------------------------------

## AWS EC2 Deployment Steps

1. Launch an Ubuntu EC2 instance.
2. Configure Security Group:
   - Allow SSH (Port 22)
   - Allow HTTP (Port 80)

3. Connect via SSH:

ssh ubuntu@<your-ec2-public-ip>

4. Install Docker:

sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ubuntu

Logout and login again.

5. Install Docker Compose:

sudo apt install docker-compose -y

Verify installation:

docker-compose --version

6. Clone the repository:

git clone <your-repository-url>
cd <project-folder>

7. Build and start containers:

docker-compose up --build -d

8. Open in browser:

http://<your-ec2-public-ip>

------------------------------------------------------------

## API Endpoint

Base URL:

/api/tutorials

Supported operations:

GET    /api/tutorials
GET    /api/tutorials/:id
POST   /api/tutorials
PUT    /api/tutorials/:id
DELETE /api/tutorials/:id

------------------------------------------------------------

## CI/CD Configuration

The repository includes CI/CD configuration to automatically build and validate the Docker setup on every push to the main branch.

The pipeline performs:
- Code checkout
- Docker image build validation
- Docker Compose validation

CI configuration files are located in:

.github/workflows/

------------------------------------------------------------

## Troubleshooting

Rebuild containers:

docker-compose up --build -d

View logs:

docker logs backend
docker logs nginx

Stop all containers:

docker-compose down

------------------------------------------------------------

## Submission

This repository contains:

- All Dockerfiles
- docker-compose.yml
- Nginx configuration
- Complete source code
- CI/CD configuration
- Setup and deployment documentation
