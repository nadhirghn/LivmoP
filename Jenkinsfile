pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }


        stage('Build and Push Docker Images') {
            steps {
              sh "docker-compose build"
              sh "docker-compose up -d"
            }
        }

    }
}
