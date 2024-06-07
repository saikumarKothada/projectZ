pipeline {
    agent any
    environment {
        TEST_SERVER_CREDENTIAL = credentials('a0a5b13a-9f82-425d-a320-7213231b8f2a')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Push to Prod') {
            steps {
                // Add steps to copy Git files to the prod server
                sh 'sshpass -p ${TEST_SERVER_CREDENTIAL_PSW} scp ${WORKSPACE}/push-to-prod ${TEST_SERVER_CREDENTIAL_USR}@10.1.0.6:/home/Saikumar/'
            }
        }
    }
}
