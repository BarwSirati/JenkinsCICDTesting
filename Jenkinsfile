pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                label 'test'
            }
            steps {
                sh 'docker build -t registry.gitlab.com/barwsirati/jenkinscicdtesting ./app'
            }
        }
    }
}
