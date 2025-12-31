pipeline {
    agent any

    stages {
        stage ('Build') {
            steps {
                echo 'Building...'
            }
        }
         stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}