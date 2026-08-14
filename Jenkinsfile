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


                withCredentials([usernamePassword(credentialsId: 'aws-cli', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) {
                    sh '''
                        echo "hello s3!" > index.html
                        aws s3api create-bucket --bucket test123 
                        aws s3 cp index.html s3://test123/
                    '''
                }



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