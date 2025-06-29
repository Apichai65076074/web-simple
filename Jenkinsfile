pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
    git branch: 'master', url: 'https://github.com/Apichai65076074/my-project-01.git'
  }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-web-cicd .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker rm -f my-web || true'
                bat 'docker run -d --name my-web -p 8888:80 my-web-cicd'
            }
        }
    }
}