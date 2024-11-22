Docker Apache Web Server
Overview
This project demonstrates how to create a lightweight, containerized web server using Docker and Apache. It includes a simple Dockerfile to build the image, a custom index.html file for the website, and instructions to run the web server in a Docker container.

Features
Base Image: Uses Ubuntu as the base image.
Apache Installation: Installs and configures Apache HTTP Server.
Custom Webpage: Serves a sample index.html file.
Port Mapping: Exposes the web server on a custom host port.

Setup Instructions

1. Clone the Repository

git clone https://github.com/fratyaln/docker-apache-webserver.git
cd docker-apache-webserver

2. Build the Docker Image

docker build -t apache-server:v1 .

3. Run the Docker Container

docker run -itd --name apache-web -p 81:80 apache-server:v1

4. Access the Web Server
Open your browser and go to:

http://localhost:81

Project Structure
bash
Copy code
docker-apache-webserver/
├── Dockerfile        # Defines the Docker image configuration
├── index.html        # Simple webpage served by Apache
└── README.md         # Project documentation


How It Works
The Dockerfile sets up an Ubuntu-based environment with Apache installed.
A custom index.html file is copied into the Apache web root directory.
The container runs Apache in the foreground, serving the webpage on port 80 (mapped to port 81 on the host).
