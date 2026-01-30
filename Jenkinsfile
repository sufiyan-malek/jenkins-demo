pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sufiyan-malek/jenkins-demo.git'
            }
        }

        stage('Run Script') {
            steps {
                sh '''
                  chmod +x details.sh
                  ./details.sh
                '''
            }
        }
    }
}
