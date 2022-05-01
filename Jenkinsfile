pipeline {
    // agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
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
                    sh 'echo "retrying"'
                }

                timeout(time: 3, unit:'MINUTES') {
                sh 'echo "Doing health check, the deploy has not completed in 3 minutes.'
                }
            }  
        }
    }
}