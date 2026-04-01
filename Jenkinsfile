pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/RounikaAcharya/node-jenkins-project'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t node-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 3000:3000 node-app'
            }
        }
    }
}