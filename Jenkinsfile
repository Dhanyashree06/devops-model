
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'GitHub checkout successful'
            }
        }

        stage('Testing') {
            steps {
                bat 'if not exist index.html exit /b 1'
                echo 'HTML file test passed'
            }
        }

        stage('Deployment') {
            steps {
                bat 'if not exist deployed mkdir deployed'
                bat 'copy /Y index.html deployed\\index.html'
                echo 'Deployment completed'
            }
        }
    }

    post {
        success {
            echo 'Pipeline SUCCESS'
        }
        failure {
            echo 'Pipeline FAILED'
        }
    }
}
