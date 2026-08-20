pipeline {
    agent any
    stages {
        
        /*
        stage('install docker'){
            steps {
                sh '''
                    rm -f Dockerfile
                    
                    echo "FROM amazon/aws-cli" > Dockerfile
                    echo "RUN yum update -y" >> Dockerfile
                    echo "RUN yum install docker -y" >> Dockerfile

                    docker build -t myimage:01 .
                '''
            }
        }
        */

        stage('aws stage') {
            agent {
                docker {
                    //image 'amazon/aws-cli'
                    image 'ubuntu:latest'
                    reuseNode true
                    args "-u 0 -v /var/run/docker.sock:/var/run/docker.sock --entrypoint=''"
                } 
            }
            steps {
                withCredentials([usernamePassword(credentialsId: 'aws-cli', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) {
                    sh '''
                        
                        # vars
                            region='us-east-1'
                            cluster='mycluster'
                            service='myservice'
                            task_definition='mytask-definition'
                            registry='792752059287.dkr.ecr.us-east-1.amazonaws.com'
                        
                        # ubuntu server

                        apt install -y jq
                        apt install -y docker 
                        #yum install jq -y
                        #yum install docker -y

                        echo "FROM amazon/aws-cli" > Dockerfile
                        docker build -t $registry/build:01 .

                        #echo "--- list services ---"

                        #aws ecs list-clusters --region $region
                        #aws ecs list-task-definitions --region $region
                        #aws ecs list-services --cluster $cluster --region $region

                        #echo "--- /list services ---"

                        # aws trying ECS commands
                            #echo "--- list revisions ----"
                            #register=$(aws ecs register-task-definition --cli-input-json file://task-definition.json --region $region | jq ".taskDefinition.revision")
                            #echo "register version: $register"
                            #echo "--- /list revisions ----"

                            #aws ecs update-service --cluster $cluster --service $service --task-definition $task_definition:$register --region $region    
                            #aws ecs wait services-stable --cluster $cluster --services $service --region $region


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
