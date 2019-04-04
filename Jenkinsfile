pipeline {
    agent none
    environment {
        LC_ALL = 'en_US.UTF-8'
        LANG = 'en_US.UTF-8'
    }
    stages {
        stage('Release iOS') {
            agent {
                docker {
                    image 'eddumelendez/fastlane'
                }
            }
            steps{
                sh 'pwd'
                sh 'cd ios'
                sh 'fastlane beta'
            }
        }

        stage('Release Android') {
            agent {
                docker {
                    image 'eddumelendez/fastlane'
                }
            }
            steps{
                sh 'pwd'
                sh 'cd android'
                sh 'fastlane beta'
            }
        }
    }
}
