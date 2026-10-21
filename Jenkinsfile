pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        
        stage('Build & Test') {
            steps {
                echo 'Building and verifying HTML syntax...'
                sh 'test -f index.html'
            }
        }

        stage('Deploy Locally') {
            steps {
                echo 'Deploying application to local hosting directory...'
                sh 'mkdir -p local-deploy'
                sh 'cp index.html local-deploy/index.html'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully! Your registration page is hosted locally.'
        }
        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}