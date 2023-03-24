pipeline {
    agent any
    environment {
        
        DOCKERHUB_CREDENTIALS = credentials('docker_key')
    }
    stages {
        stage('git checkout') {
            steps {
                git branch: 'main', credentialsId: 'raji_git', url: 'https://github.com/rajeeb007/docker.git'
            }
        }
    }
}