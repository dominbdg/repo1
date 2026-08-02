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
                echo 'Hello World'
            }
        }
    }
}
