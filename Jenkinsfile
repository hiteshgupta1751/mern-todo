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
                    # Stop and remove existing containers to avoid name conflicts
                    docker compose down --remove-orphans
                    docker compose up -d --build
                '''
            }
        }
    }
}

