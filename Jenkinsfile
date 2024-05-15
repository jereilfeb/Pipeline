pipeline {
    agent any
    stages{
        stage('Git Checkout') {
            steps {
                // Checkout your Git Repository
                git url:'https://github.com/jereilfeb/Pipeline.git', branch: 'main'
            }
        }
    stage ('Insta Dependencies') {
        steps {
            sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
        stage('Build') {
            steps {
                
            }
        }
    }
    }

