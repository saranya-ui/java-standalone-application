pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'Maven 3.9.3'
    }

    stages {
        stage('Check JDK Path') {
  steps {
    sh 'ls -l /Library/Java/JavaVirtualMachines/openjdk-17.jdk/Contents/Home/bin/java'
  }
}

        stage('Check Environment') {
            steps {
                sh '''
                   echo "JAVA_HOME=$JAVA_HOME"
                   echo "PATH=$PATH"
                   type -a java
                   ${JAVA_HOME}/bin/java -version
                   export JAVA_HOME=${JAVA_HOME}
                   export PATH=${JAVA_HOME}/bin:$PATH
                   mvn -version
                   which sh
                   sh -c "echo shell is working"
                '''
            }
        }
    }
}
