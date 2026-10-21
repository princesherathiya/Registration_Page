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
                echo 'Verifying index.html...'
                bat 'dir index.html'
            }
        }

        stage('Deploy to Local Server Folder') {
            steps {
                echo 'Deploying to local directory for Python server...'
                bat 'if not exist C:\\local-server-folder mkdir C:\\local-server-folder'
                bat 'copy index.html C:\\local-server-folder\\index.html'
            }
        }
    }
    
    post {
        success {
            echo 'Deployment successful! Python server directory updated.'
        }
    }
}