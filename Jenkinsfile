pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-creds', url: 'https://github.com/Nihat58/arscom.git', branch: 'main'
            }
        }

        stage('Test') {
            steps {
                echo 'Kod başarıyla çekildi. Jenkins pipeline çalışıyor.'
            }
        }
    }
}
