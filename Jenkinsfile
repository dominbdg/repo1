pipeline {
    agent any

    stages {
        stage('Hello') {
            agent any
            steps {
                sh '''
                    echo " testing first stage"
                    echo "aaa" > echo.txt
                    ls -alh 
                    #echo "FROM debian:latest" > Dockerfile
                    #docker build -t debian:mod .
                    #docker pull ububntu
                    pwd
                    ls -al 
                '''
            }
        }
        stage('check docker version') {
            steps {
                sh '''
                    echo "testing second stage"
                    pwd
                    ls -alh

                '''
            }
        }    
    }
}
