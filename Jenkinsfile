pipeline {
    agent any
    stages {
        stage('aws stage') {
            agent {
                docker {
                    image 'amazon/aws-cli'
                    args "--entrypoint=''"
                } 
            }
            steps {

                sh '''
                    aws s3 ls


                '''

            }



        }


    }





}




/*
pipeline {
    agent { label 'linux-10.10.0.43' }

    stages {
        stage('Test') {
            steps {
                sh '''
                    mkdir /tmp/test    
                '''
            }
        }
    }
}
*/