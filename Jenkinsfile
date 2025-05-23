pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Deploy') {
            steps {
                bat 'echo Hello World'
            }
        }
    }
}
