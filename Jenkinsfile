pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "hello world"'
                sh '''
                 echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}