pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''
                    echo "FROM debian:latest" > Dockerfile
                    docker build -t debian:mod .
  
       
                '''
            }
        }     
    }
}
