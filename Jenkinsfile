
pipeline {
    agent any

    stages {
        stage('Checkout Source Code') {
            steps {
                echo 'Pulling code from Git repository...'
                checkout scm
            }
        }

        stage('Build & Execute Script') {
            steps {
                echo 'Checking Python version...'
                bat 'python --version'

                echo 'Running exp.py...'
                bat 'python exp.py'
            }
        }

        stage('Code Stability Check') {
            steps {
                echo 'Verifying pipeline execution...'
                bat 'echo Python script executed successfully!'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: CI Pipeline completed successfully!'
        }
        failure {
            echo 'FAILURE: Pipeline failed. Check build logs.'
        }
        always {
            echo 'Pipeline execution finished.'
        }
    }
}
