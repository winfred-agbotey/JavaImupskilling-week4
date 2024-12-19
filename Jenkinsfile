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
                    sh 'mvn clean compile'

            }
        }
        stage('Test') {
            steps {
                    sh 'mvn test'

            }
            post {
                            success {
                                echo "Unit tests completed successfully"
                            }
                            failure {
                                echo "Unit tests failed"
                            }
                        }
        }
        stage('Package') {
            steps {
                    sh 'mvn package'

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