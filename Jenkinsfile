pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This pulls your code from GitHub
                checkout scm
            }
        }
        stage('Deploy Locally') {
            steps {
                // This creates a folder inside Jenkins and moves your index.html there
                sh 'mkdir -p /var/jenkins_home/deployed_site'
                sh 'rsync -avz index.html /var/jenkins_home/deployed_site/'
                echo 'Successfully moved index.html to the local deployment folder!'
            }
        }
        stage('Verify') {
            steps {
                // This proves the file actually made it there
                sh 'ls -la /var/jenkins_home/deployed_site'
                sh 'cat /var/jenkins_home/deployed_site/index.html'
            }
        }
    }
}
