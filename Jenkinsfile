pipeline {
    agent any

    environment {
        IMAGE_NAME = "capstone-app"
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/YOUR-USERNAME/capstone-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop capstone-container || true
                docker rm capstone-container || true
                docker run -d -p 3000:3000 --name capstone-container $IMAGE_NAME
                '''
            }
        }
    }
}
