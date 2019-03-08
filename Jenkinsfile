pipeline {
    agent { docker { image 'linuxbrew/brew' } }
    stages {
        stage('build') {
            steps {
                sh 'export LC_ALL=en_US.UTF-8'
                sh 'export LANG=en_US.UTF-8'
                sh 'brew --version'
                sh 'brew install rbenv'
                sh 'rbenv init'
                sh 'fastlane beta'
            }
        }
    }
}
