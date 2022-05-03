pipeline {
    // agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
    agent any
    stages {
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
    }
}