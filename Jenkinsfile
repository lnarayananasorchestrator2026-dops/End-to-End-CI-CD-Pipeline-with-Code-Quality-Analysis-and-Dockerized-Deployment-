pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/lnarayananasorchestrator2026-dops/End-to-End-CI-CD-Pipeline-with-Code-Quality-Analysis-and-Dockerized-Deployment-'
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
                sh 'docker run -d -p 8080:8080 poc-app || true'
            }
        }
    }
}
