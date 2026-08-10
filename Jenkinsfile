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
                script {
                   env.myvar="abc"     
                }
            }
        }
        stage('deploy') {
            steps {
                echo "myvar is: $myvar"
            }
        }        
    }
}
