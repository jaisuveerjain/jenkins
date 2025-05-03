pipeline {
    agent any

    stages {
        stage('Clean') {
            steps {
                echo 'Data file is cleaned and sorted'
            }
        }
        
        stage('Deploy') {
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
            steps {
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt
                    sleep 10
                    exit 1
                '''
            }
        }
        stage('Test Linux') {
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
