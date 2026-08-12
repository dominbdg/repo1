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
                    echo " testing first stage"
                    echo "aaa" > echo.txt
                    ls -alh 
                '''
            }
        }
        stage('check docker version') {
            steps {
                sh '''
                    echo "testing second stage"
                    ls -alh

                '''
            }
        }    
    }
}
