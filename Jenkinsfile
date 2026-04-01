pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t node-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker stop node-container || exit 0'
                bat 'docker rm node-container || exit 0'
                bat 'docker run -d -p 3000:3000 --name node-container node-app'
            }
        }
    }
}