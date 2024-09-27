# Dockerized-Flask-Web-App
This project is a basic Dockerized Flask Web Application designed to demonstrate how a Python-based web app can be containerized and deployed using Docker. The app is built using the lightweight Flask framework and responds with a simple "Hello, Docker!" message when accessed. It serves as an excellent starting point for understanding how to use Docker to package and deploy Python applications, making the deployment process easier and more portable across different environments.

# Create the Project Directory

mkdir docker-flask-app

cd docker-flask-app

# Create a Flask Application 

Inside the folder create a Python file

# Create a requirements.txt File

Add Flask as a dependency

# Create a Dockerfile

//Use an official Python runtime as a parent image

FROM python:3.9-slim

//Set the working directory

WORKDIR /app

//Copy the current directory contents into the container

COPY . /app

//Install any needed packages specified in requirements.txt

RUN pip install --no-cache-dir -r requirements.txt

//Make port 5000 available to the world outside this container

EXPOSE 5000

//Define environment variable

ENV NAME World

//Run app.py when the container launches

CMD ["python", "app.py"]

# Create a .dockerignore File
To avoid copying unnecessary files

# Build and Run the Docker Container

//Build

docker build -t flask-app 

//Run

docker run -p 5000:5000 flask-app

Now you should see the app running on localhost:5000

# Features

Containerization: The entire Flask application runs in a Docker container, ensuring consistent and reliable deployments across various environments.

Lightweight: Uses Python's slim image for a minimal Docker image footprint, making it faster to build and deploy.

Portability: The application can run on any platform that supports Docker, whether it's Linux, macOS, or Windows.

Simplicity: The app is simple and easy to understand, serving as a perfect starting point for learning how to containerize applications.

Extensibility: Easily extend the project by adding more routes, connecting to databases, or deploying it on cloud platforms like AWS or Google Cloud.

# Prerequisites

Docker: Make sure Docker is installed on your system. You can install Docker from here.

Basic Knowledge of Flask: While the app is simple, a basic understanding of Flask will help you extend the project further if needed.
