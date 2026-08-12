pipeline {
    agent any

    stages {
        stage('create file') {
            agent any
            steps {
                sh '''
                    echo " testing first stage"
                    echo "aaa" > echo.txt
                    ls -alh 
                    #echo "FROM debian:latest" > Dockerfile
                    #docker build -t debian:mod .
                    #docker pull ububntu
                    pwd
                    ls -al 
                '''
            }
        }
        stage('check file') {
            steps {
                sh '''
                    echo "testing second stage"
                    pwd
                    ls -alh

                '''
            }
        }

        parallel {
            stage('stage1') {
                        steps {
                            sh '''
                                echo "this is pararrel stage1"
                                pwd
                                ls -alh

                            '''
                        }
                    }

          stage('stage2') {
                        steps {
                            sh '''
                                echo "this is pararrel stage2"
                                pwd
                                ls -alh

                            '''
                        }
                    }
        }    
    }
}
