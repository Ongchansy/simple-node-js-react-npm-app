pipeline {
    agent any

    stages {
        stage ('Build') {
            steps {
                sh 'npm install --save-dev'
            }
        }
         stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}