pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("simple-node-js-react-npm-app:latest")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh "docker rm -f react-app || true"
                    docker.image("simple-node-js-react-npm-app:latest")
                          .run("--name react-app -d -p 3001:3000")
                }
            }
        }
    }
}
