pipeline {
    agent any
    environment {
        LC_ALL = 'en_US.UTF-8'
        LANG = 'en_US.UTF-8'
    }
    stages {
        stage('Release iOS') {
            steps{
                sh 'npm install'
                sh '(cd ios && bundle install && fastlane beta)'
            }
        }

        stage('Release Android') {
            steps{
                sh 'npm install'
                sh '(cd android & fastlane beta)'
            }
        }
    }
}
