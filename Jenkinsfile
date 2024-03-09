pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output PES1UG21CS076.cpp'
                    echo 'Build Stage Successful'
                }
            }
            post {
                always {
                    catchError {
                        sh 'echo "Build stage completed"'
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './output'
                    echo 'Test Stage Successful'
                }
            }
            post {
                always {
                    catchError {
                        sh 'echo "Test stage completed"'
                    }
                }
            }
        }
        
        // stage('Deploy') {
        //     steps {
        //         echo 'Deployment Successful'
        //     }
        //     post {
        //         always {
        //             catchError {
        //                 sh 'echo "Deploy stage completed"'
        //             }
        //         }
        //     }
        // }

        stage('Deploy') {
  steps {
    script {
      sh 'exit 1' // This will exit the script with a non-zero code, simulating a deployment failure
    }
  }
}

    }
    post {
        always {
            catchError {
                echo 'Pipeline failed'
            }
        }
    }
}
