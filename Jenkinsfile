pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'pwd' 
            }
        }
        stage('deploy') {
            steps {
                echo "myvar is: $myvar"
            }
        }        
    }
}
