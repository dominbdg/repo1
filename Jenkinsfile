pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                '''
                    echo "FROM debian:latest" > Dockerfile
                '''
            }
        }     
    }
}
