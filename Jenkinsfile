pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("simple-node-js-react-npm-app:latest", "-f DockerFile .")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("simple-node-js-react-npm-app:latest").run("-d -p 3001:3001")
                }
            }
        }
    }
}
