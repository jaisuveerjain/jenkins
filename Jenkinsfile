pipeline {
    agent none
    stages {
        stage('Clean') {
            agent { label 'master' }
            steps {
                sh '''
                echo 'Data file is cleaned and sorted'
                ls -lrt
                python3 --version
                python3 script.py
                '''
            }
        }
        
        stage('Deploy') {
            agent { label 'master' }
            steps {
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt
                '''
            }
        }
        stage('TestALL'){
            parallel {
                stage('TestWindows') {
                agent { label 'slave' }
                steps {
                    sh '''
                        #!/bin/bash
                        sleep 1
                    '''
                }
            }
                stage('Test') {
                agent { label 'slave' }
                steps {
                    sh '''
                        #!/bin/bash
                        sleep 1
                    '''
                    }
                }
            }
        }
        stage('Validate Results') {
            agent { label 'master' }
            steps {
                sh """
                    #!/bin/bash
                    sleep 1
                """
            }
        }
    }
}
