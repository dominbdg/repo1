pipeline {
    agent any
    stages {
        stage('aws stage') {
            agent {
                docker {
                    //image 'amazon/aws-cli'
                    image 'ubuntu:latest'
                    reuseNode true
                    args "-u 0 --entrypoint=''"
                } 
            }
            steps {


                withCredentials([usernamePassword(credentialsId: 'a9b40f90-93e6-44ed-8599-0ce1295eb886', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) 
                {
                    sh '''
                        region='us-west-1'
                        registry='792752059287.dkr.ecr.us-east-1.amazonaws.com'
                        version="01"

                        apt update -y
                        apt install awscli

                            #echo "hello s3!" > index.html
                            #aws s3api create-bucket --bucket test-202608142248
                            #mkdir temp        
                            #ouch temp/aaa
                            #touch temp/bbb
                            
                            # --- building docker image ----
                       
                            #yum update -y
                            #yum install docker -y
                            #cat /etc/group

                            #echo "FROM amazon/aws-cli" > Dockerfile
                            #docker build -t $registry/aws:$version .  

                              
                        #echo "show entire directory..."
                        #pwd
                        #    #cd temp
                        #   d aws ecs list-task-definitions --region $region
                        #    aws ecs register-task-definition --cli-input-json file://task-definition.json --region $region
                        #    aws ecs update-service --cluster cluster2 --service myservice --task-definition mytask:11 --region $region
                        #    aws ecs list-clusters --region $region
                        #    echo "$BUILD_ID"
                        
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
