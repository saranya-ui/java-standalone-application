

pipeline {
    agent any

    tools {
        jdk 'jdk8'       // Must exactly match your Global Tool Configuration name
        maven 'Maven 3.9.3' // Same here
    }

    stages {
        
        stage('Checkout') {
            steps {
                git url: 'https://github.com/expertszen/java-standalone-application.git', branch: 'main'
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
