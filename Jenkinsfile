pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Alina690574/devopsfinalproject.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker compose build'
            }
        }

        stage('Stop Old Containers') {
            steps {
                bat 'docker compose down'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                bat '''
                docker compose down
                docker compose up -d --build
                '''
            }
        }
    }
}
