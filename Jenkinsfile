pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t student-registration .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f student-registration-container || true'
                sh 'docker run -d --restart unless-stopped --name student-registration-container -p 8081:80 student-registration'
            }
        }
    }
}
