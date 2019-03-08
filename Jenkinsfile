pipeline {
    agent {
        docker {
            image 'paasmule/rbenv'
        }
    }
    environment {
        LC_ALL = 'en_US.UTF-8'
        LANG = 'en_US.UTF-8'
    }
    stages {
        stage('build') {
            steps {
                sh 'brew --version'
                sh 'rbenv init'
                sh 'brew cask install fastlane'
                sh 'fastlane beta'
            }
        }
    }
}
