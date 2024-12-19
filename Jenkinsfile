pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/winfred-agbotey/JavaImupskilling-week4'
            }
        }
        stage('Build') {
            steps {
                dir('TestingFrameworks') {
                    sh 'mvnw.cmd clean compile'
                }
            }
        }
        stage('Test') {
            steps {
                dir('TestingFrameworks') {
                    sh 'mvnw.cmd test'
                }
            }
        }
        stage('Package') {
            steps {
                dir('TestingFrameworks') {
                    sh 'mvnw.cmd package'
                }
            }
        }
    }

    post {
        success {
            echo 'Build, Test, and Packaging were successful!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}