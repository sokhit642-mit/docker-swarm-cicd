pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code is checked out by Jenkins.'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ksk6699/docker-swarm-cicd:1.0.0 .'
            }
        }

        stage('Test') {
            steps {
                sh 'docker image inspect ksk6699/docker-swarm-cicd:1.0.0'
            }
        }
    }

    post {
        success {
            echo 'Build and test completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the console output.'
        }
    }
}
