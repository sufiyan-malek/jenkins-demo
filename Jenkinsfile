pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/sufiyan-malek/jenkins-demo.git'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t jenkins-demo:1.0 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run --rm jenkins-demo:1.0'
            }
        }
    }
}
