pipeline {
    agent any

    stages {
        stage('Hello') {
            agent {
                docker {
                    image "ubuntu:latest"
                }
            }
            steps {
                sh '''
                    #echo "FROM debian:latest" > Dockerfile
                    #docker build -t debian:mod .
                    #docker pull ububnto
                    ls -al 
                '''
            }
        }
        stage('check docker version') {
            steps {
                sh 'docker image ls'
            }
        }    
    }
}
