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
                    image 'eddumelendez/fastlane'
                    args '-w ios'
                }
            }
            steps{
                sh 'cd ./ios'
                sh 'fastlane beta'
            }
        }
    }
}
