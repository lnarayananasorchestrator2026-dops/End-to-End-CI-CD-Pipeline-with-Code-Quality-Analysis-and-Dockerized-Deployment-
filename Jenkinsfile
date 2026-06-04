pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/<your-username>/poc-cicd-java.git'
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
