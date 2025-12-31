pipeline {
    agent any

    stages {

        stage('Debug Workspace') {
            steps {
                sh '''
                pwd
                echo "==== LIST FILES ===="
                ls -la
                echo "==== CHECK DOCKERFILE ===="
                ls -lh Dockerfile || echo "Dockerfile NOT FOUND"
                '''
            }
        }

        stage('Build Image') {
            steps {
                sh '''
                docker build -t simple-node-js-react-npm-app:latest .
                '''
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f react-app || true
                docker run -d --name react-app -p 3001:3000 simple-node-js-react-npm-app:latest
                '''
            }
        }
    }
}
