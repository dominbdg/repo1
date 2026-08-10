pipeline {
    agent any

    stages {
        stage('Hello') {
            agent any
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
