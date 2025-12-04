pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/hiteshgupta1751/mern-todo.git'
            }
        }

        stage('Deploy App') {
            steps {
                sh '''
                    cd $WORKSPACE
                    docker compose down
                    docker compose up -d --build
                '''
            }
        }
    }
}

