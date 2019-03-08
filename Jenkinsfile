pipeline {
    agent {
        docker {
            image 'linuxbrew/brew'
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
                sh 'brew install rbenv'
                sh 'rbenv init'
                sh 'fastlane beta'
            }
        }
    }
}
