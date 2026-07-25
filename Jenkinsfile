pipeline {
    agent any

    environment {
        IMAGE_NAME = "golang-cicd-demo"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %IMAGE_NAME% .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run --rm %IMAGE_NAME%'
            }
        }

    }

    post {
        success {
            echo 'Pipeline Completed Successfully'
        }

        failure {
            echo 'Pipeline Failed'
        }
    }
}

  