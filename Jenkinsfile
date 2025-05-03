pipeline {
    agent any

    stages {
        stage('Clean') {
            steps {
                echo 'Data file is cleaned'
            }
        }
        
        stage('Deploy') {
            steps {
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt
                    sleep 20
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt
                    sleep 20
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
