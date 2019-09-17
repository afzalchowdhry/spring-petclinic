pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh './mvnw clean compile'
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
            }
        }
        stage('Release') {
            steps {
                sh './mvnw package'
				sh
            }
        }
        stage('Deploy') {
            steps {
                sh script: '''chmod +x start.sh
                export BUILD_ID=dontKillMe
                export JENKINS_NODE_COOKIE=dontKillMe
                ./start.sh'''
            }
        }
    }
}
