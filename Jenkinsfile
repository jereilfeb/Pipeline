pipeline {
    agent
    

    stages{
        stage('Checkout') {
            steps {
                // Checkout your Git Repository
                git 'https://github.com/jereilfeb/Pipeline.git'
            }
        }
    stage ('Build Docker Image') {
        steps {
            // Build your Docker Image
            script {
                dockerImage = docker.build('node-app:latest')
            }
        }
    }
    }
}