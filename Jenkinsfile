pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
 stage('Verify Tools') {
            steps {
                script {
              
                        // Check if Docker is installed and accessible
                        sh 'docker --version'
                        
                        // Check if Docker Compose is installed and accessible
sh '/usr/local/bin/docker-compose --version'
                        
                    
                }
            }
        }

     stage('Build and Deploy') {
            steps {
                script {
                    // Define the path to your Docker Compose file
                    
                    // Build the containers defined in the Docker Compose file
                    sh "docker-compose -f docker-compose.yml build"
                    
                    // Start the containers in detached mode (background)
                    sh "docker-compose -f docker-compose.yml up -d"
                }
            }
        }

    }
}
