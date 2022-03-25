pipeline {
    agent any

    stages {
        stage('Clone The Repo') {
            steps {
                git 'https://github.com/ankitkumawat509/GitSession.git'
            }
        }
        stage('Build the latest image') {
            steps {
                sh "docker build -t php:latest ."
            }
        }
        stage('Push image to regitry') {
            steps {
                sh "docker push ankitkumawat/docrepo:latest"
            }
        stage('Deploy container ') {
            steps {
                sh "docker run -d -p 8082:8082 ankitkumawat/docrepo:latest"
            }

        }
    }
}
