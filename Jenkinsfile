// pipeline{

//     agent any
//     tools{
//         maven "maven"
//         //tools like docker also
//     }
//     environment{
//         VERSION_NAME="1.34"
//     }

//     stages{
//         stage("compile"){
//             // when{
//             //     expression{

//             //     }
//             // }
//             steps{
//                 sh 'javac Test.java'
//                 sh 'echo "${VERSION_NAME}"'
//             }
//         }
//         stage("run"){
//             steps{
//                 sh "java Test"
//             }
//         }

//     }

//     post{

//         always{
//             sh 'echo "always"'
//         }

//         success{
//             sh 'echo "success"'
//         }

//         failure{
//             sh 'echo "failure"'
//         }

//     }
// }

pipeline {
    agent any
    tools {
        maven "maven"
    }
    environment {
        VERSION_NAME = "1.34"
    }

    stages {
        stage("compile") {
            steps {
                if (isUnix()) {
                    sh 'javac Test.java'
                } else {
                    bat 'javac Test.java'
                }
                if (isUnix()) {
                    sh 'echo "${VERSION_NAME}"'
                } else {
                    bat 'echo %VERSION_NAME%'
                }
            }
        }
        stage("run") {
            steps {
                if (isUnix()) {
                    sh 'java Test'
                } else {
                    bat 'java Test'
                }
            }
        }
    }

    post {
        always {
            if (isUnix()) {
                sh 'echo "always"'
            } else {
                bat 'echo always'
            }
        }
        success {
            if (isUnix()) {
                sh 'echo "success"'
            } else {
                bat 'echo success'
            }
        }
        failure {
            if (isUnix()) {
                sh 'echo "failure"'
            } else {
                bat 'echo failure'
            }
        }
    }
}