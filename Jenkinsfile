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
        
        stage('docker image building') {

            steps {

                sh 'docker build -t rajeeb007/docker-helloworld1 .'
               
            }

        }
        stage('Login') {

            steps {

                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'

            }

        }
        stage('pushing to docker hub') {

            steps {

                sh 'docker push rajeeb007/docker-helloworld1'

            }

        }
    }
    post{

            always {  

                sh 'docker logout'   

            }      
            
        }
}