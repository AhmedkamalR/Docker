# Express.js Application with Docker, Docker Compose, and Docker Swarm

This repository contains a simple Express.js application that is dockerized and can be orchestrated using Docker Compose or Docker Swarm. The setup includes MongoDB and PostgreSQL as databases, Nginx as a reverse proxy, and Watchtower for automated container updates.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Directory Structure](#directory-structure)
- [Docker Compose Setup](#docker-compose-setup)
- [Docker Swarm Setup (Optional)](#docker-swarm-setup-optional)
- [Customization](#customization)
- [Monitoring](#monitoring)
- [Maintenance](#maintenance)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Docker Swarm](https://docs.docker.com/swarm/install-manually/) (Optional)

## Getting Started

1. **Clone this repository:**

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```
2. **Create environment files:**
  ```bash
  cp env/.env.example .env
  cp env/postgres.env.example postgres.env
  cp env/mongodb.env.example mongodb.env
  Customize these files according to your requirements.
```
3. **Build and start the Docker containers:**
  ```bash
  docker-compose up -d
  ```
4. **Access your application:**
  Visit http://localhost to access your Express app. Nginx will proxy requests to the app.
-- Directory Structure
  - app/: Contains your Express.js application code.
  - env/: Contains environment variable templates.
  - docker-compose.yml: Defines the services and configurations for Docker Compose.
  - docker-stack.yml: Defines the services and configurations for Docker Swarm (Optional).
  - nginx/: Contains Nginx configuration files.
  - postgres/: Contains PostgreSQL data files.
  - mongodb/: Contains MongoDB data files.
 **Docker Compose Setup:**
 ## Services
  ## Express App:
   - Accessible at http://localhost
   - Edit your Express app code in the app directory.
 ## PostgreSQL:
   - Host: postgres
   - Port: 5432
   - Username and password from postgres.env
   - Database name from .env
## MongoDB:
  - Host: mongodb
  - Port: 27017 
  - Username and password from mongodb.env
  - Database name from .env
## Nginx:
  - Acts as a reverse proxy for the Express app.
## Watchtower:
  - Monitors your Docker containers for updates and automatically pulls and restarts containers when a new image is available.
## Docker Swarm Setup (Optional):
  If you want to run this setup in a Docker Swarm cluster, follow these steps:
  - 1.**Initialize a Docker Swarm:**
    ```bash
    docker swarm init
    ```
  - 2.**Deploy the stack:**
    ```bash
    docker stack deploy -c docker-stack.yml <stack-name>
    ```
 - 3.**Access your services:** as described above, but use the node's IP or hostname instead of localhost.
## Customization:
- Customize the services, environment variables, and configurations in the docker-compose.yml file (or docker-stack.yml for Swarm) to fit your application's needs.
- You can add more services to the YAML file as your application grows.
## Monitoring:
- Use docker service logs <service-name> to view logs for a specific service.
- Consider integrating monitoring tools like Prometheus and Grafana for more in-depth monitoring.
## Maintenance:
- Use Watchtower to automatically update your containers with the latest images.
- Regularly back up your database data volumes.
## Contributing
- Feel free to open issues or contribute to this project.
 

 











