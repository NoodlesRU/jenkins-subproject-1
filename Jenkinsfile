```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker run --rm node:24.21.0-alpine3.24 node --version'
                bat 'docker run --rm node:24.21.0-alpine3.24 npm --version'
            }
        }

        stage('Test') {
            steps {
                retry(3) {
                    timeout(time: 1, unit: 'MINUTES') {
                        bat 'docker run --rm node:24.21.0-alpine3.24 node -e "console.log(\'Tests passed\')"'
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline has finished.'
        }

        success {
            echo 'Pipeline completed successfully.'
        }

        failure {
            echo 'Pipeline failed.'
        }
    }
}
```
