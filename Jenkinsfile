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
                dir('testingframework') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage('Test') {
            steps {
                dir('testingframework') {
                    sh 'mvn test'
                }
            }
        }
        stage('Package') {
            steps {
                dir('testingframework') {
                    sh 'mvn package'
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