pipeline{

    agent any
    tools{
        maven "maven"
        //tools like docker also
    }
    environment{
        VERSION_NAME="1.34"
    }

    stages{
        stage("compile"){
            // when{
            //     expression{

            //     }
            // }
            steps{
                sh 'javac Test.java'
                sh 'echo "${VERSION_NAME}"'
            }
        }
        stage("run"){
            steps{
                sh "java Test"
            }
        }

    }

    post{

        always{
            sh 'echo "always"'
        }

        success{
            sh 'echo "success"'
        }

        failure{
            sh 'echo "failure"'
        }

    }
}