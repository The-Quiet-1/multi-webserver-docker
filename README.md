# Web Hoster – Multi Webserver Hosting Using Docker

This repository demonstrates how to host two different web servers (Apache and Nginx) simultaneously using Docker and Docker Compose.<br>
It is designed for students, DevOps beginners, and anyone who wants to learn container-based hosting in a simple and practical way.

# 1. Project Structure
web_Hoster/<br>
│<br>
├── apache/<br>
│   └── index.html → Website page served by Apache<br>
│<br>
├── nginx/<br>
│   └── index.html → Website page served by Nginx<br>
│<br>
└── docker-compose.yml → Main configuration file<br>

# 2. Purpose of This Project

Running multiple web servers on the same machine normally causes conflicts because both try to use the same ports.<br>
Docker solves this by running each server inside its own isolated container.

This project helps you understand:<br>

How containers isolate applications<br>

How multiple servers can run simultaneously<br>

How Docker Compose manages multiple services<br>

How to host simple websites using Docker<br>

# 3. Features

Two fully working web servers: Apache and Nginx<br>

Separate index.html for each server<br>

Clean Docker Compose setup<br>

Beginner-friendly configuration<br>

Runs on any OS that supports Docker<br>

Stop/start everything with one command<br>

# 4. Description

This repository provides a containerized multi-webserver environment using Docker and Docker Compose.<br>
It demonstrates lightweight hosting of multiple static websites through Apache and Nginx, running in isolated containers on a single host system.

The project is suitable for:<br>

DevOps practice<br>

Docker learning<br>

Multi-environment simulation<br>

Web hosting demonstrations<br>

Container networking basics<br>

# 5. docker-compose.yml
version: '3.8'

services:
  nginx_server:
    image: nginx:latest
    container_name: nginx_server
    ports:
      - "8081:80"
    volumes:
      - ./nginx:/usr/share/nginx/html
    restart: always

  apache_server:
    image: httpd:latest
    container_name: apache_server
    ports:
      - "8082:80"
    volumes:
      - ./apache:/usr/local/apache2/htdocs/
    restart: always

# 6. How to Run the Project

Step 1: Install Docker<br>
Make sure Docker and Docker Compose are installed on your system.

Step 2: Clone the Project

git clone https://github.com/The-Quiet-1/multi-webserver-docker
cd web_Hoster


Step 3: Start Both Web Servers<br>

docker-compose up -d


Step 4: Visit in Browser<br>

Server	URL
Nginx	http://localhost:8081

Apache	http://localhost:8082

Step 5: Stop Everything<br>

docker-compose down

# 7. Full Commands List
Docker Commands
docker ps
docker stop container_name
docker start container_name
docker logs container_name
docker exec -it container_name bash

Docker Compose Commands
docker-compose up
docker-compose up -d
docker-compose down
docker-compose restart
docker-compose ps

# 8. Future Improvements (Optional Enhancements)

Add load balancer (Nginx reverse proxy)<br>

Enable HTTPS using Certbot<br>

Add a database container<br>

Add environment variables<br>

Add CI/CD pipeline (GitHub Actions)<br>

Add logging and monitoring (Prometheus + Grafana)<br>
