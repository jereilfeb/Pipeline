pipeline {
    agent any
    stages{
        stage('Git Checkout') {
            steps {
                // Checkout your Git Repository
                git url:'https://github.com/jereilfeb/Pipeline.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build .'
            }
        }
    }
    }

