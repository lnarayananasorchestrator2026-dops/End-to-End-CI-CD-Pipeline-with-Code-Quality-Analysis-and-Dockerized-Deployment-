pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                
            git branch: 'main', url: 'https://github.com/lnarayananasorchestrator2026-dops/End-to-End-CI-CD-Pipeline-with-Code-Quality-Analysis-and-Dockerized-Deployment-.git'

            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t poc-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f poc-app || true'
                sh 'docker run -d -p 5000:8080 --name poc-app poc-app'

            }
        }
        
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                   sh 'mvn sonar:sonar'
        }
    }
}

    }
}
