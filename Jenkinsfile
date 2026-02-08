pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Alina690574/devopsfinalproject.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Stop Old Containers') {
            steps {
                sh 'docker compose down'
            }
        }

       stage('Deploy with Docker Compose') {
    steps {
        sh '''
        docker compose down || true
        docker compose up -d --build
        '''
    }
}

    }
}