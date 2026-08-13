pipeline {
    agent { label 'linux-10.10.0.43' }

    stages {
        stage('Test') {
            steps {
                sh '''
                    hostname
                    whoami
                    java -version
                '''
            }
        }
    }
}