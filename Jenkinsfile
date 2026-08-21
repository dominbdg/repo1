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
                            d='Dockerfile'
                        
                        # building docker image

                        apt update -y
                        apt install ca-certificates curl awscli -y
                        install -m 0755 -d /etc/apt/keyrings
                        curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
                        chmod a+r /etc/apt/keyrings/docker.asc


                        rm -f Dockerfile
                        echo "FROM ubuntu:latest" > Dockerfile
                        echo "RUN apt update -y" >> Dockerfile
                        echo "RUN apt install ca-certificates curl awscli -y" >> Dockerfile
                            #apt install ca-certificates curl
                        echo "RUN install -m 0755 -d /etc/apt/keyrings" >> Dockerfile
                        echo "RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc" >> Dockerfile
                        echo "RUN chmod a+r /etc/apt/keyrings/docker.asc" >> Dockerfile

                        echo "Types: deb" > /etc/apt/sources.list.d/docker.sources
                        echo "URIs: https://download.docker.com/linux/ubuntu" >> /etc/apt/sources.list.d/docker.sources
                        echo "Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")" >> /etc/apt/sources.list.d/docker.sources
                        echo "Components: stable" >> /etc/apt/sources.list.d/docker.sources
                        echo "Architectures: $(dpkg --print-architecture)" >> /etc/apt/sources.list.d/docker.sources
                        echo "Signed-By: /etc/apt/keyrings/docker.asc" >> /etc/apt/sources.list.d/docker.sources

                        echo "COPY /etc/apt/sources.list.d/docker.sources /etc/apt/sources.list.d/docker.sources" >> Dockerfile
                        #cat docker.source
                        
                        echo "RUN apt update -y" >> Dockerfile
                        echo "RUN apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin" >> Dockerfile
                        
                        echo "----------------------------------------"

                        #apt update -y && apt install -y docker
                        apt update -y
                        apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

                        docker build -t debian:01 .

                        #docker-buildx --version

                        #yum install jq -y
                        #yum install docker -y

                        # --- deployment from registry ---    
                        #echo "FROM amazon/aws-cli" > Dockerfile

                        
                        #aws ecr get-login-password --region $region | docker login --username AWS --password-stdin $registry
                        #docker build -t $registry/myrepo:01 --provenance=false --push .
                        #docker push $registry/myrepo:01

                        #docker build -t $registry/build:01 .
                        #aws ecr get-login-password --region $region | docker login --username AWS --password-stdin $registry
                        #docker push $registry/myrepo

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
