pipeline {
    agent any
    options {
        timeout(time: 30, unit: 'SECONDS')
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
        stage('Activate Environment') {
            agent {
                label 'unittest'
            }
            steps {
                sh 
                '''#!/bin/bash
                 source env/bin/activate && pip install -r ./requirements.txt
                '''
            }
        }
    }
}
