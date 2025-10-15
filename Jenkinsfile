// pipeline {
//     agent any

//     tools {
//         jdk 'jdk8'  // Use the exact name you set in Jenkins (step 1)
//         maven 'Maven 3.9.3'
//     }

//     stages {
//         stage('Check JDK Path') {
//             steps {
//                 sh 'ls -l $JAVA_HOME/bin/java'
//             }
//         }

//         stage('Check Environment') {
//             steps {
//                 sh '''
//                    echo "JAVA_HOME=$JAVA_HOME"
//                    echo "PATH=$PATH"
//                    type -a java
//                    $JAVA_HOME/bin/java -version
//                    mvn -version
//                    which sh
//                    sh -c "echo shell is working"
//                 '''
//             }
//         }
//     }
// }

pipeline {
    agent any

    tools {
        jdk 'jdk8'       // Must exactly match your Global Tool Configuration name
        maven 'Maven 3.9.3' // Same here
    }

    stages {
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
