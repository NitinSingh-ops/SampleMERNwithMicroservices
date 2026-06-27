pipeline {
    agent any

    stages {
        stage('Git Version') {
            steps {
                bat 'git --version'
            }
        }

        stage('Docker Version') {
            steps {
                bat 'docker --version'
            }
        }

        stage('Build Frontend') {
            steps {
                bat 'docker build -t frontend ./frontend'
            }
        }

        stage('Build Hello Service') {
            steps {
                bat 'docker build -t hello-service ./backend/helloService'
            }
        }

        stage('Build Profile Service') {
            steps {
                bat 'docker build -t profile-service ./backend/profileService'
            }
        }

        stage('Docker Images') {
            steps {
                bat 'docker images'
            }
        }
    }
}