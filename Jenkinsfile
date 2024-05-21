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
                sh 'docker build -t jereilfeb23/node-app . '
            }
        stage('Deploy') [
            steaps [
                withCredentials([usernamePassword(credentioansId: "$[DOCKER_REGISTRY_CREDS]", passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                    sh "echo \$DOCKER_PASSWORD | docker login -u \$DOCKER_USERNAME --password-stdin docker.io"
                    sh 'docker push $DOCKER_BFLASK_IMAGE'
                }
            ]
        ]
        }
    }
    }

