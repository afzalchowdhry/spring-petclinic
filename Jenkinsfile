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
            }
        }
        stage('Deploy') {
            steps {
                sh 'chmod +x start.sh'
                sh 'export JENKINS_NODE_COOKIE=dontKillMe'
                sh "./start.sh"
            }
        }
    }
}
