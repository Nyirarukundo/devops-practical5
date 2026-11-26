pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Installing dependencies...'
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Building and deploying Docker container...'
                bat 'docker build -t devops-web-app .'
                bat 'docker stop my-web-app || exit 0'
                bat 'docker rm my-web-app || exit 0'
                bat 'docker run -d -p 3000:3000 --name my-web-app devops-web-app'
            }
        }
    }
}