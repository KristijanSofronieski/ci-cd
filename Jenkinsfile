pipeline {
    agent any

    stages {
        stage('Deploy to Server') {
            steps {
                
                sshagent(['deploy-key']) {
                    
                    
                    sh 'rsync -avz -e "ssh -o StrictHostKeyChecking=no" . ubuntu@172.29.80.1:/home/Kris/my-project'
                    
                }
            }
        }
    }
}