pipeline {
    agent any
environment {
        PYTHON = '/usr/bin/python3' // Adjust the path as needed
    }
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
        stage('Push to Docker Hub') {
    steps {
        script {
            // Log in to Docker Hub with your Docker Hub username and access token
            sh 'docker login -u livmo -p dckr_pat_kNb_Fd8a08r_lWQwytcwMN0vADI'
            sh "docker push livmo/git_integraion_server:latest"
            sh "docker push livmo/git_integraion_frontend:latest"

        }
    }
}


    }
}
