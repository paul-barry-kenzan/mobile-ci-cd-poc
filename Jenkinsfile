pipeline {
    agent { docker { image 'linuxbrew/brew' } }
    stages {
        stage('build') {
            steps {
                sh 'export LC_ALL=en_US.UTF-8'
                sh 'export LANG=en_US.UTF-8'
                sh 'echo LC_ALL'
                sh 'brew --version'
                sh 'sudo brew cask install fastlane'
                sh 'fastlane beta'
            }
        }
    }
}
