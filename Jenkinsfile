pipeline {
    agent none
    environment {
        LC_ALL = 'en_US.UTF-8'
        LANG = 'en_US.UTF-8'
    }
    stages {
        stage('build') {
            steps{
                sh 'pwd'
                sh 'cd ios'
                sh 'fastlane beta'
            }
        }
    }
}
