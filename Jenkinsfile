pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                bat '''
                    if not exist index.html exit /b 1
                    echo HTML file exists
                '''
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                    if not exist C:\\JenkinsDeploy mkdir C:\\JenkinsDeploy
                    copy /Y index.html C:\\JenkinsDeploy\\index.html
                '''
            }
        }
    }
}
