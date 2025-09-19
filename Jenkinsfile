pipeline {
    agent any

    options {
        disableConcurrentBuilds() 
    }

    stages {
        stage('Checkout'){
            steps {
                git url: 'https://github.com/1994subhasmita-commits/subha_patra.git', 
                    branch: 'main', 
                    credentialsId: 'github_apps' 
            }
        }

        stage('Prallel Stages') {
            parallel {
                stage('Check code quality repo1'){
                    steps {
                        sh '''
                            pwd 
                            ls -lrt
                            exit 1
                        '''
                    }
                }

                stage('Build'){
                    steps {
                        sh '''
                            pwd 
                            ls -lrt
                            sleep 10
                        '''
                    }
                }
            }
        }

        stage('stage_final') {
            steps{
                echo "This is final stage"
            }
        }
      
    }

}
