pipeline {
    agent any
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
                sh 'echo deliver for development'
            }
        }
        stage('Deploy for production') {
            when {
                branch 'production'  
            }
            steps {
                // install helm
                sh '/opt/homebrew/bin/wget https://get.helm.sh/helm-v3.6.1-linux-amd64.tar.gz'
                sh 'ls -a'
                sh 'tar -xvzf helm-v3.6.1-linux-amd64.tar.gz'
                sh 'sudo cp linux-amd64/helm /usr/bin'
                sh 'helm version'


                // deploy with helm
                sh 'echo deliver for production'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'echo finished'
            }
        }
    }
}
