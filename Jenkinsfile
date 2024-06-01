pipeline {
    agent any
    stages {
        stage('Checkout Main Repository') {
            steps {
                dir('my-subdirectory') {
                    checkout scm
                }
            }
        }
        // Add more stages as needed
    }
}
