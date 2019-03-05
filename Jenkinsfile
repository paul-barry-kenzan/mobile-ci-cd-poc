pipeline {
    agent { docker { image 'ruby:latest' } }
    stages {
        stage('build') {
            steps {
                sh 'sudo gem install fastlane -NV'
                sh 'fastlane beta'
            }
        }
    }
}