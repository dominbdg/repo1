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
                    image 'myimage:01'
                    reuseNode true
                    args "-u 0 -v /var/run/docker.sock:/var/run/docker.sock --entrypoint=''"
                } 
            }
            steps {
                withCredentials([usernamePassword(credentialsId: 'aws-cli', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) {
                    sh '''
                        region='us-east-1'
                        cluster='mycluster'
                        
                        echo "--- list services ---"

                        aws ecs list-clusters --region $region
                        aws ecs list-task-definitions --region $region
                        aws ecs list-services --cluster $cluster --region $region

                        echo "--- /list services ---"

                        aws ecs register-task-definition --cli-input-json file://task-definition.json
                    

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
