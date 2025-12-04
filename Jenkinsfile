pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/hiteshgupta1751/mern-todo.git'
            }
        }

        stage('Update Local Project') {
            steps {
                sh '''
                    cd /root/mern-todo
                    git pull
                '''
            }
        }

        stage('Deploy App') {
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

