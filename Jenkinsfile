pipeline {
    agent any

    environment {
        IMAGE_NAME = 'flask-app'
        CONTAINER_NAME = 'flask-app'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/randiveyuvrani/Automated-Docker-Image-Deployment-to-Amazon-ECR-with-Jenkins-and-Lambda-Intergration.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t $IMAGE_NAME .'
                }
            }
        }

        stage('Stop and Remove Old Container') {
            steps {
                script {
                    sh 'docker stop $CONTAINER_NAME || true'
                    sh 'docker rm $CONTAINER_NAME || true'
                }
            }
        }

        stage('Run Container on Port 8000') {
            steps {
                script {
                    sh 'docker run -d -p 8000:5000 --name $CONTAINER_NAME $IMAGE_NAME'
                }
            }
        }
    }
}
