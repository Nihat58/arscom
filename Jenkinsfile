pipeline {
    agent any
    stages {
        stage('GitHub Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    extensions: [
                        [$class: 'CloneOption', 
                         depth: 1,  // Sadece son commit'i çeker
                         shallow: true]
                    ],
                    userRemoteConfigs: [[
                        credentialsId: 'github-ssh',
                        url: 'git@github.com:nihat58/repo.git'
                    ]]
                ])
            }
        }
    }
}
