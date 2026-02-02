pipeline {
    agent any

    stages {

        stage('Build Image') {
            steps {
                sh 'docker build -t demoapp:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f demoapp || true'
                sh 'docker run --name demoapp demoapp:v1'
            }
        }

    }
}
