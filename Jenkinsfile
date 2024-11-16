pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', credentialsId: 'github-cred', url: 'https://github.com/javeedmeeran077/Docker-CICD-Jenkins-Nodejs.git'
            }
        }
        stage('Build Image') {
            steps {
                script {
                    sh 'docker build -t nodejs-app:latest .'
                }
            }
        }
        stage('Run Container') {
            steps {
                script {
                    sh 'docker run -d -p 3005:3005 --name nodejs-app nodejs-app:latest'
                }
            }
        }
    }
}
