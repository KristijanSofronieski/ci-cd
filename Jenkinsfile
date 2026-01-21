pipeline {
    agent any

    stages {
        stage('Deploy to Server') {
            steps {
                // 'ubuntu' is the name of your credential ID in Jenkins
                sshagent(['ubuntu']) {
                    sh "rsync -avz -e 'ssh -o StrictHostKeyChecking=no' . ubuntu@172.29.80.1:/home/Kris/my-project"
                }
            }
        }
    }
}
