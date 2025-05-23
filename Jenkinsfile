pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Deploy to AWS') {
            steps {
                sshagent(['aws-ssh-key']) {
                    sh '''
                    scp -o StrictHostKeyChecking=no * ec2-user@YOUR_EC2_IP:/var/www/html/
                    ssh -o StrictHostKeyChecking=no ec2-user@YOUR_EC2_IP "sudo systemctl restart httpd"
                    '''
                }
            }
        }
    }
}
