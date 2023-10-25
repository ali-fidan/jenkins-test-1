pipeline {
    agent any

    stages {


        stage('Build Docker Image') {
            steps {
                // Docker imajını oluştur
                script {
                    sh 'docker image build -t webimage:${BUILD_NUMBER} .'
                }
            }
        }


        stage('Deploy') {
            steps {
                // Sunucuda Docker imajını başlat
                script {
                    sh 'docker rm -f frontend'
                    sh 'docker run -dp 80:80 --name frontend webimage:${BUILD_NUMBER}' // Veya başka bir komut ile imajı başlatın
                }
            }
        }
    }
}
