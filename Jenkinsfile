pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building Calculator App...'
                sh 'python --version' // Verify Python is installed
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh 'python calculator.py'
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving Results...'
                archiveArtifacts artifacts: '*.py', allowEmptyArchive: true
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
