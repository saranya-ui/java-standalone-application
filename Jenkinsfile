pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'Maven 3.9.3'
    }

    stages {
        stage('Check Environment') {
            steps {
                sh 'echo "JAVA_HOME=$JAVA_HOME"'
                sh 'echo "PATH=$PATH"'
                sh 'which java'
                sh 'java -version'
                sh 'which mvn'
                sh 'mvn -version'
                sh 'which sh'
                sh 'sh -c "echo shell is working"'
            }
        }
    }
}
