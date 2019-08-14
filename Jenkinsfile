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
                sh 'docker build -t spring-petclinic:1.0 .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d --name spring-petclinic -p 8090:8090 localhost/spring-petclinic:1.0'
            }
        }
    }
}
