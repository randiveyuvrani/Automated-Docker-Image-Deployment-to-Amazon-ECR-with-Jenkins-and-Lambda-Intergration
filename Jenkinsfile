pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/randiveyuvrani/Automated-Docker-Image-Deployment-to-Amazon-ECR-with-Jenkins-and-Lambda-Intergration.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t flask-app .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker stop flask-app || true && docker rm flask-app || true'
                    sh 'docker run -d -p 8000:5000 --name flask-app flask-app'
                }
            }
        }
    }
}
