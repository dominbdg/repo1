pipeline {
    agent any
    stages {
        stage('aws stage') {
            agent {
                docker {
                    image 'amazon/aws-cli'
                    reuseNode true
                    args "--entrypoint=''"
                } 
            }
            steps {


                withCredentials([usernamePassword(credentialsId: 'aws-cli', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) 
                {
                    sh '''
                        echo "hello s3!" > index.html
                        #aws s3api create-bucket --bucket test-202608142248
                        mkdir temp        
                        touch temp/aaa
                        touch temp/bbb
                        
                        echo "show entire directory..."
                        ls -al
                        cd temp
                        aws s3 sync . s3://test-202608142248/
                    '''
                }



            }



        } //stage


    } //stages
} //pipeline




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