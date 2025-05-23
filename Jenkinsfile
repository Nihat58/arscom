pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Nihat58/arscom.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'apache-server',
                            transfers: [
                                sshTransfer(
                                    sourceFiles: '**/*',
                                    removePrefix: '',
                                    remoteDirectory: '/var/www/html',
                                    execCommand: 'sudo systemctl restart apache2'
                                )
                            ]
                        )
                    ]
                )
            }
        }
    }
}
