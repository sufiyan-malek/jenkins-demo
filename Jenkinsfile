pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sufiyan-malek/jenkins-demo.git'
            }
        }

        stage('Run Script') {
            steps {
                sh '''
                  chmod +x app.sh
                  ./app.sh
                '''
            }
        }
    }
}
