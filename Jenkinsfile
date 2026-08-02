pipeline {
    agent any

    stages {
        stage('Hello') {
            agent {
              docker {
                image 'debian:latest'
              }
            }
            steps {
                sh '''
                echo 'Hello World'
                hostname
                '''
            }
        }
    }
}
