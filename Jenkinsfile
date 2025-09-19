pipeline {
    agent any

    options {
        timeout(time: 1 unit: 'MINUTES')  // Stop pipeline after 5 min
    }

    parameters {
        booleanParam(name: 'RUN_BUILD', defaultValue: true, description: 'Run Build Stage?')
    }

    stages {
        stage('Checkout') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'github_apps', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh '''
                        echo "Cloning repo with user: $USER"
                        git clone https://$USER:$PASS@github.com/1994subhasmita-commits/subha_patra.git

                    '''
                }
            }
        }

        stage('Build') {
            when { expression { return params.RUN_BUILD } }  // Runs only if RUN_BUILD=true
            steps {
                sh '''
                    echo "Building the project..."
                    sleep 70
                '''
            }
        }

        stage('Final') {
            steps {
                echo "This is the final stage"
            }
        }
    }
}
