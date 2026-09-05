pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code downloaded from GitHub'
            }
        }

        stage('Build') {
            steps {
                bat 'docker build -t jenkins-cicd-app .'
            }
        }

        stage('Test') {
            steps {
                bat 'if exist index.html (echo TEST PASSED) else (exit /b 1)'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Application ready for deployment'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}