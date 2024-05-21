pipeline {
    agent any
    
    tools {
        jdk 'jdk17'
    }
    
      environment {
        SCANNER_HOME=tool 'sonar-scanner'
    }

    stages {
        stage('Git Checkout') {
            steps {
                git url:'https://github.com/jereilfeb/Pipeline.git', branch: 'main'
            }
        }
        
        stage('OWASP Dependency') {
            steps {
                dependencyCheck additionalArguments: '--scan ./ ', odcInstallation: 'DC'
                dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
            }
        }
        stage('Trivy FS') {
            steps {
               sh "trivy fs ."
            }
        }
        stage(" Sonarqube Analysis "){
            steps{
                 withSonarQubeEnv('sonar') {
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Dotnet-demo \
                    -Dsonar.projectKey=Dotnet-demo '''
                    
                 }
            }
        } 
        
    }
}