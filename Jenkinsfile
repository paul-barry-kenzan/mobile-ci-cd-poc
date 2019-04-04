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
                sh 'cd ios && fastlane beta'
            }
        }

        stage('Release Android') {
            agent {
                docker {
                    image 'eddumelendez/fastlane'
                }
            }
            steps{
                sh 'cd android & fastlane beta'
            }
        }
    }
}
