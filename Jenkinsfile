pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-web-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker stop my-web-app || true
                docker rm my-web-app || true
                docker run -d -p 80:80 --name my-web-app my-web-app
                '''
            }
        }
    }
}
