 pipeline {
    agent any
    stages {
        stage('git'){
         steps {
            git url: 'https://github.com/saikumarKothada/projectZ.git'
         }
        } 
        stage('Checkout') {
            steps {
                dir('my-directory') {
                    checkout scm
                }
            }
        }
    }
}
