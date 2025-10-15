pipeline {
    agent any

    tools {
        jdk 'jdk8'  // Use the exact name you set in Jenkins (step 1)
        maven 'Maven 3.9.3'
    }

    stages {
        stage('Check JDK Path') {
            steps {
                sh 'ls -l $JAVA_HOME/bin/java'
            }
        }

        stage('Check Environment') {
            steps {
                sh '''
                   echo "JAVA_HOME=$JAVA_HOME"
                   echo "PATH=$PATH"
                   type -a java
                   $JAVA_HOME/bin/java -version
                   mvn -version
                   which sh
                   sh -c "echo shell is working"
                '''
            }
        }
    }
}
