pipeline {
    agent any
    stages{
        stage('Git Checkout') {
            steps {
                // Checkout your Git Repository
                git url:'https://github.com/jereilfeb/Pipeline.git', branch: 'main'
            }
        }
    stage ('Build Docker Image') {
        steps {
            // Build your Docker Image
            sh 'docker build -t jereilfeb/node-app:latest'
            }
        }
        stage('Test Image') {
            steps {
                echo 'Testing...'
                sh 'docker inspect -type=image jereilfeb/node-app:v3'
            }
        }
    }
    }

