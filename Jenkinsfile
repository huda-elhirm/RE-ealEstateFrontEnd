pipeline {
    agent any
    tools {
        nodejs 'NodeJs' // This should match the name you gave in Global Tool Configuration
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
