pipeline {
    agent any

    stages {
        stage('Build React App') {
            steps {
                script {
                    docker.image('node:18-alpine').inside {
                        sh 'npm install'
                        sh 'npm run build'
                    }
                }
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build/**', fingerprint: true
        }
    }
}
