pipeline {
    agent any
    

    stages{
        stage('Git Checkout') {
            steps {
                // Checkout your Git Repository
                git branch: 'main' git url:'https://github.com/jereilfeb/Pipeline.git'
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
