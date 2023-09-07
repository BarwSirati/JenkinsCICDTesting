pipeline {
    agent any
    options {
        timeout(time: 60, unit: 'SECONDS')
    }
    stages {
        stage('Install Environment') {
            agent {
                label 'test'
            }
        }
        stage('Run Container') {
            agent {
                label 'test'
            }
            steps {
                sh '''#!/bin/bash
                 source env/bin/activate && pip install -r ./requirements.txt
                '''
            }
        }
    }
}
