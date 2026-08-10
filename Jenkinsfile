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
                cat /etc/hosts
                hostname
                '''
            }
        }
    }
}
