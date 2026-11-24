pipeline {
    agent any
    stages {
        stage('Baixar Código do GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/lukkyzdev/MeuSite-DevOps.git'
            }
        }
        stage('Enviar para o AWS S3') {
            steps {
                withAWS(credentials: 'aws-s3-creds', region: 'us-east-2') {
                    s3Upload(
                        bucket: 'site-jenkins-lucas-2026-655887417298-us-east-2-an',
                        file: 'index.html',
                        path: 'index.html'
                    )
                }
            }
        }
    }
}
