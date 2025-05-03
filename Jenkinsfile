pipeline {
    agent none
    stages {
        stage('Clean') {
            agent { label 'slave' }
            steps {
                echo 'Data file is cleaned and sorted'
            }
        }
        
        stage('Deploy') {
            agent { label 'master' }
            steps {
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt
                    sleep 10
                '''
            }
        }
        stage('Test') {
            agent { label 'slave' }
            steps {
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt
                    sleep 10
                '''
            }
        }
        stage('Test Linux') {
            agent { label 'master' }
            steps {
                sh """
                    #!/bin/bash
                    pwd
                    ls -lrt
                    sleep 20
                """
            }
        }
    }
}
