pipeline {
    agent any

    stages {
        stage('Build React App') {
            steps {
                script {
                    docker.image('node:18-alpine').inside {
                        sh 'npm install'
                    }
                }
            }
        }
    }
}
