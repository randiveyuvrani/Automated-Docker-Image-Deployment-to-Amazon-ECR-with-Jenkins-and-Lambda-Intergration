pipeline {
    agent any

    environment {
        IMAGE_NAME = "flask-app"
        BUILD_TAG = "${BUILD_NUMBER}"  // Jenkins build number
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/randiveyuvrani/Automated-Docker-Image-Deployment-to-Amazon-ECR-with-Jenkins-and-Lambda-Intergration.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${IMAGE_NAME}:${BUILD_TAG} ."
                }
            }
        }

        stage('Run Docker Container (Optional)') {
            when {
                expression { return false } // ✅ Prevent running a new container
            }
            steps {
                script {
                    sh "docker run -d -p 8001:5000 --name ${IMAGE_NAME}_${BUILD_TAG} ${IMAGE_NAME}:${BUILD_TAG}"
                }
            }
        }
    }
}
