pipeline {
    agent any
    tools {
        nodejs 'NodeJs' // Ensure this matches the name in Global Tool Configuration
    }
    environment {
        DOCKER_CREDENTIALS_ID = 'realestate1234' // Replace with your Docker Hub credentials ID
        IMAGE_NAME = 'realestate1234/react-front' // Replace with your Docker Hub username and desired image name
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
                sh 'npm run build' // Assuming you have a build script in your package.json
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    def imageTag = "${IMAGE_NAME}:${env.BUILD_NUMBER}"
                    docker.build(imageTag)
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    // Push the Docker image to Docker Hub
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS_ID) {
                        def imageTag = "${IMAGE_NAME}:${env.BUILD_NUMBER}"
                        docker.image(imageTag).push('latest') // Push the latest tag
                    }
                }
            }
        }
    }
}
