pipeline {
    agent any

    stages {

        stage('Git Version') {
            steps {
                sh 'git --version'
            }
        }

        stage('Docker Version') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Build Frontend') {
            steps {
                sh 'docker build -t frontend ./frontend'
            }
        }

        stage('Build Hello Service') {
            steps {
                sh 'docker build -t hello-service ./backend/helloService'
            }
        }

        stage('Build Profile Service') {
            steps {
                sh 'docker build -t profile-service ./backend/profileService'
            }
        }

        stage('Docker Images') {
            steps {
                sh 'docker images'
            }
        }
    }
}
