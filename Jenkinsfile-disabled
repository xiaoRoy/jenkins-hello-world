pipeline {
    agent any

    environment {
        TEST_ENGINE = 'JUnit'
    }

    stages {


        stage('Test') {
            steps {
                sh './gradlew check -Dorg.gradle.java.home=/Library/Java/JavaVirtualMachines/jdk-11.0.14.jdk/Contents/Home'
            }
        }
    }
    post {
        always {
            junit 'build/reports/**/*.xml'
        }
    }
}
