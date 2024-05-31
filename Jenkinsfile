 pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                dir('my-directory') {
                    checkout scm
                }
            }
        }
    }
}
