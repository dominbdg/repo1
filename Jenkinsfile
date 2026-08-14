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
                    export AWS_ACCESS_KEY_ID="AKIA3RE5UOOL6QXNHZ4K"
                    export AWS_SECRET_ACCESS_KEY="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" 
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