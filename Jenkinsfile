pipeline {

    agent any

    stages {

        stage('Build Docker Image') {

            steps {

                sh 'docker build -t my-app .'

            }

        }

        stage('Run Docker Container') {

            steps {

                sh '''
                docker rm -f my-container || true

                docker run -d -p 80:80 --name my-container my-app

                '''

            }

        }

    }

}