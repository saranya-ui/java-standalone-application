pipeline {
    agent any

      tools {
        maven 'Maven 3.9.3'
          jdk 'jdk17'
    }

    environment {
        // Append Maven and Homebrew bin to PATH correctly
        PATH = "${tool 'Maven 3.9.3'}/bin:/opt/homebrew/bin:/usr/bin:/bin:/usr/sbin:/sbin"
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

// pipeline {
//     agent any

//     tools {
//         maven 'Maven 3.9.3'
//     }

//     environment {
//         // Append Maven and Homebrew bin to PATH correctly
//         PATH = "${tool 'Maven 3.9.3'}/bin:/opt/homebrew/bin:/usr/bin:/bin:/usr/sbin:/sbin"
//     }

//     stages {
//         stage('Check Shell and Maven') {
//             steps {
//                 sh 'which sh'
//                 sh 'sh -c "echo Shell found and working"'
//                 sh 'mvn -version'
//             }
//         }
//     }
// }

