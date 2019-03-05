pipeline {
    agent { docker { image 'rubylang/ruby:2.6.0-bionic' } }
    stages {
        stage('build') {
            steps {
                sh 'brew cask install fastlane'
                sh 'fastlane beta'
            }
        }
    }
}