pipeline {
    agent any
    options {
        timeout(time: 60, unit: 'SECONDS')
    }
    stages {
        stage('Install Environment') {
            agent {
                label 'unittest'
            }
            steps {
                sh 'python3 -m venv env'
            }
        }
        stage('Activate Environment && Install Library') {
            agent {
                label 'unittest'
            }
            steps {
                sh '''#!/bin/bash
                 source env/bin/activate && pip install -r ./requirements.txt
                '''
            }
        }
        stage('Run Unittest') {
            agent {
                label 'unittest'
            }
            steps {
                sh '''#!/bin/bash
                 source env/bin/activate && python3 ./unit_test.py
                '''
            }
        }
        stage('Run Robot') {
            agent {
                label 'unittest'
            }
            steps {
                echo 'Create Container'
                sh 'docker compose -f ./compose.yaml up -d'
                echo 'Cloning Robots'
                git branch: 'main', url: 'https://github.com/CE-SDPX/simple-api-robot.git'
                echo 'Runing Robot'
                sh 'ls -al'
            }
        }
    }
}
