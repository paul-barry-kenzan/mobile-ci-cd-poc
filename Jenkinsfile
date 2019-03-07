pipeline {
    agent { docker { image 'fastlanetools/fastlane' } }
    stages {
        stage('build') {
            steps {
                sh 'export LC_ALL=en_US.UTF-8'
                sh 'export LANG=en_US.UTF-8'
                sh 'cd ios'
                sh 'fastlane beta'
            }
        }
    }
}