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
                sh 'source ./env/bin/activate'
                sh 'pip install -r ./requirements.txt'
            }
        }
    }
}
