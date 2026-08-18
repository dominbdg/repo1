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


                withCredentials([usernamePassword(credentialsId: 'a9b40f90-93e6-44ed-8599-0ce1295eb886', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) 
                {
                    sh '''
                        echo "hello s3!" > index.html
                            #aws s3api create-bucket --bucket test-202608142248
                            #mkdir temp        
                            #ouch temp/aaa
                            #touch temp/bbb
                        
                        echo "show entire directory..."
                        pwd
                            #cd temp
                            aws ecs list-task-definitions
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
