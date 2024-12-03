pipeline {
    agent any
    tools {
        nodejs 'NodeJs' // Ensure 'NodeJs' is configured in Manage Jenkins -> Global Tool Configuration
    }
    /*environment {
        DOCKER_CREDENTIALS_ID = 'dockerhub-credentials' // Replace with your Jenkins credential ID for Docker Hub
        IMAGE_NAME = 'realestate1234/react-frontend' // Replace with your Docker Hub repository
    }*/
    stages {
        stage('Install Dependencies') { 
            steps {
                sh 'npm install' // Install Node.js dependencies
            }
        }
        stage('Build React App') {
            steps {
                sh 'npm run build' // Build the React app
            }
        }
       /* stage('Build Docker Image') {
            steps {
                script {
                    // Define image tag
                    def imageTag = "${IMAGE_NAME}:latest"
                    // Build the Docker image
                    sh 'docker build -t ${imageTag} .'
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    // Push the Docker image to Docker Hub
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS_ID) {
                        def imageTag = "${IMAGE_NAME}:${env.BUILD_NUMBER}"
                        sh 'docker push ${imageTag}' // Push versioned tag
                        sh 'docker tag ${imageTag} ${IMAGE_NAME}:latest' // Tag as latest
                        sh 'docker push ${IMAGE_NAME}:latest' // Push latest tag
                    }
                }
            }
        }*/
    }
}
