pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''
                    echo "FROM debian:latest" > Dockerfile
                    docker built -t debian:mod .
  
       
                '''
            }
        }     
    }
}
