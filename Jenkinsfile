pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker run --rm node:24.21.0-alpine3.24 node --version'
            }
        }

        stage('Test') {
            steps {
                bat 'docker run --rm node:24.21.0-alpine3.24 npm --version'
            }
        }
    }
}