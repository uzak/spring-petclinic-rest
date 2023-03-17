pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'java --version'
            }
        }
        stage('Test') {
            steps {
                sh 'echo Test Stage'
            }
        }
        stage('Deliver for development') {
            when {
                branch 'development' 
            }
            steps {
                sh 'echo deliver for development"
            }
        }
        stage('Deploy for production') {
            when {
                branch 'production'  
            }
            steps {
                sh 'echo deliver for development"
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'echo finished'
            }
        }
    }
}
