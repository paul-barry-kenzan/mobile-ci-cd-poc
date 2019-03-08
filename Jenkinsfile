pipeline {
    agent none
    environment {
        LC_ALL = 'en_US.UTF-8'
        LANG = 'en_US.UTF-8'
    }
    stages {
        stage('build') {
            agent {
                docker {
                    image 'paasmule/rbenv'
                }
            }
            steps {
                sh 'brew --version'
                sh 'rbenv init'
            }
        }
        stage('Fastlane') {
            agent {
                docker {
                    image 'fastlanetools/fastlane'
                }
            }
            steps{
                sh 'brew install fastlane'
                sh 'fastlane beta'
            }
        }
    }
}
