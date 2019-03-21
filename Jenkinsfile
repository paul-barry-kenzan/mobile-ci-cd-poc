pipeline {
    agent any
    environment {
        LC_ALL = 'en_US.UTF-8'
        LANG = 'en_US.UTF-8'
    }
    stages {
        stage('build') {
            steps{
                sh 'npm install'
                sh '( cd ios && fastlane beta )'
            }
        }
    }
}
