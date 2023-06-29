pipeline {
    agent any

    stages {
        stage('Check Api Folder') {
            agent {
                label 'unittest'
            }
            steps {
                sh 'ls -al'
            }
        }
    }
}
