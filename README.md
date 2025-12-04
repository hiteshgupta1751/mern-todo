# MERN Todo App

MERN Todo App — Dockerized + CI/CD with Jenkins on AWS EC2

This is a full-stack MERN (MongoDB, Express, React, Node.js) Todo App deployed on AWS EC2 using:

Docker & Docker Compose

Jenkins CI/CD Pipeline

GitHub Webhook

Nginx Reverse Proxy (optional)

🚀 Features

Add, Edit, Delete Todo Items

Fully responsive React frontend

Node.js + Express backend

In-memory todo logic

Dockerized frontend + backend

MongoDB container

Automatic deployment via Jenkins on every Git push

🐳 Docker Setup

Run locally using:

docker compose up -d --build


Services:

Frontend: React app on port 80

Backend: Node.js API on port 5000

MongoDB: port 27017

⚙️ CI/CD Pipeline (Jenkins + GitHub)

Pipeline flow:

Developer pushes code → GitHub

GitHub Webhook triggers Jenkins

Jenkins pulls latest code

Jenkins runs:

docker compose down
docker compose up -d --build


Containers restart with the latest build

App auto-updates on AWS EC2

📁 Project Structure
mern-todo/
├── client/        # React frontend
├── server/        # Express backend
├── docker-compose.yml
├── Jenkinsfile
└── README.md

📦 Jenkinsfile (Pipeline Script)
pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/hiteshgupta1751/mern-todo.git'
            }
        }

        stage('Deploy App on EC2') {
            steps {
                sh '''
                    cd /root/mern-todo
                    docker compose down
                    docker compose up -d --build
                '''
            }
        }
    }
}

🖥️ Tech Stack

Frontend: React, Material UI

Backend: Express.js, Node.js

Database: MongoDB

CI/CD: Jenkins + GitHub Webhook

Containerization: Docker

Cloud: AWS EC2

🙌 Author

Hitesh Gupta
DevOps | Cloud | AWS | Linux | Docker | Jenkins
