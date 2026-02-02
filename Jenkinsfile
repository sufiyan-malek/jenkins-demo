pipeline {
    agent any

    environment {
        IMAGE = "demoapp"
    }

    triggers {
        githubPush()
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify Files') {
            steps {
                sh 'ls -l'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE:${BUILD_NUMBER} .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker rm -f demoapp || true'
                sh 'docker run --name demoapp $IMAGE:${BUILD_NUMBER}'
            }
        }

    }

    post {
        success {
            echo "Deployment successful"
        }
        failure {
            echo "Pipeline failed"
        }
    }
}
