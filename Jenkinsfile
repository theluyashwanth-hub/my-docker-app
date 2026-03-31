pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/theluyashwanth-hub/my-docker-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-node-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name my-container my-node-app'
            }
        }
    }
}
