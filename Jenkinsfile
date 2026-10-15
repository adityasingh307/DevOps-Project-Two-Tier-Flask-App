pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/adityasingh307/DevOps-Project-Two-Tier-Flask-App.git'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                sh '''
                    docker compose \
                      --env-file /etc/two-tier-app/.env \
                      up -d --build
                '''
            }
        }
    }
}