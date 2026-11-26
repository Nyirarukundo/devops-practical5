pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo "Building the project..."
                bat 'dir'
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                bat 'npm test'
            }
        }
    }
}