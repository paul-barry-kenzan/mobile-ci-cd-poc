pipeline {
    agent { docker { image 'rubylang/ruby:2.6.0-bionic' } }
    stages {
        stage('build') {
            steps {
                sh 'gem install fastlane -NV'
                sh 'fastlane beta'
            }
        }
    }
}