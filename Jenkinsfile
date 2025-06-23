pipeline {
    agent any

    environment {
        ECR_REPO = '577638399543.dkr.ecr.ap-south-1.amazonaws.com/flask-ecr-app'
        IMAGE_TAG = 'latest'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/randiveyuvrani/Automated-Docker-Image-Deployment-to-Amazon-ECR-with-Jenkins-and-Lambda-Intergration.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $ECR_REPO:$IMAGE_TAG .'
            }
        }

        stage('Login to ECR') {
            steps {
                sh '''
                    aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin $ECR_REPO
                '''
            }
        }

        stage('Push to ECR') {
            steps {
                sh 'docker push $ECR_REPO:$IMAGE_TAG'
            }
        }
    }
}
