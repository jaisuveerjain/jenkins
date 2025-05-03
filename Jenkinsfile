pipeline {
    agent none
    parameters{
        string name: 'ENV_NAME',
            defaultValue: 'UAT',
            description: 'Input the environment to deploy'
        
    }
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
         stage('Analyse') {
            agent { label 'master' }
            catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                steps {
                    sh '''
                    echo 'Data file is cleaned and sorted'
                    ls -lrt
                    python3 --version
                    exit 1
                    '''
                }
            }
        }
        
        stage('Deploy Preprod') {
            when {
                expression{
                    params.ENV_NAME == 'PREPROD'
                }
            }
            agent { label 'master' }
            steps {
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt
                '''
            }
        }
        stage('Deploy UAT') {
            when {
                expression{
                    params.ENV_NAME == 'UAT'
                }
            }
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
