pipeline {
    agent any

    tools {
        maven 'Maven 3.9.3' // Use the name you configured in Jenkins
    
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/expertszen/java-standalone-application.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive Test Results') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
