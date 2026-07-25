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
                sh 'docker run --rm $IMAGE_NAME'
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

  