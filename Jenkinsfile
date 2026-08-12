pipeline {
    agent any

    stages {
        stage('check file') {
            parallel {
                stage('stage1') {
                    agent any
                    steps {
                        sh '''
                            echo "stage1
                        '''
                    }
                }
                 stage('stage2') {
                    agent any
                    steps {
                        sh '''
                            echo "stage2

                        '''
                    }
                }           







        }
    }
}
}