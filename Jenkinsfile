pipeline {
    agent { docker { image 'node:10.15.2' } }
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
                sh 'node --version'
                sh 'fastlane beta'
            }
        }
    }
}