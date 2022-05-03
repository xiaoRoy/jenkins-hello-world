pipeline {
    // agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
    agent any

    environment {
        TEST_ENGINE = 'JUnit'
    }

    stages {

        stage('Test') {
            steps {
                echo "Test engine is ${TEST_ENGINE}"
            }
        }

        stage('Build') {
            steps {
                // sh 'mvn --version'
                sh 'echo "building"'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "deploying"'

                retry(3) {
                    //retry, once this step failed.
                    sh 'echo "retrying"'
                }

                timeout(time: 3, unit:'MINUTES') {
                    sh 'echo "This should be done in 3 minutes otherwise it will be failed."'
                }
            }
        }

        post {
            always {
                echo 'This will always run'
            }
            success {
                echo 'This will run only if successful'
            }
            failure {
                echo 'This will run only if failed'
            }
            unstable {
                echo 'This will run only if the run was marked as unstable'
            }
            changed {
                echo 'This will run only if the state of the Pipeline has changed'
                echo 'For example, if the Pipeline was previously failing but is now successful'
            }
        }
    }
}
