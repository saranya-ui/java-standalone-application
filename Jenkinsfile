// pipeline {
//     agent any

//     tools {
//         maven 'Maven 3.9.3' 
//     }

//     stages {
//         stage('Build') {
//             steps {
//                 sh 'mvn clean install'
//             }
//         }

//         stage('Test') {
//             steps {
//                 sh 'mvn test'
//             }
//         }

//         stage('Archive Test Results') {
//             steps {
//                 junit 'target/surefire-reports/*.xml'
//             }
//         }
//     }

//     post {
//         success {
//             echo 'Build succeeded!'
//         }
//         failure {
//             echo 'Build failed.'
//         }
//     }
// }

pipeline {
    agent any

    tools {
        maven 'Maven 3.9.3' // this tells Jenkins to use the Maven you installed in Jenkins Global Tools
    }

    stages {
        stage('Check Shell and Maven') {
            steps {
                sh 'echo "Shell location:" $(which sh)'
                sh 'echo "Maven version:" $(mvn -version)'
            }
        }
    }
}

