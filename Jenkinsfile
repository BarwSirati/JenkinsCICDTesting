pipeline {
    agent any
    stages {
        stage('Install Environment') {
            agent {
                label 'test'
            }
            steps {
                sh 'python3 -m venv env'
            }
        }
    }
}
