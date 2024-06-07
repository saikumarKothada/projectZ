pipeline {
    agent {
        label 'prod'
    }
    environment {
        TEST_SERVER_CREDENTIAL = credentials('a0a5b13a-9f82-425d-a320-7213231b8f2a')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Push to test') {
            steps {
                // Add steps to copy Git files to the test server
                sh 'sshpass -p ${TEST_SERVER_CREDENTIAL_PSW} scp -r ${WORKSPACE} ${TEST_SERVER_CREDENTIAL_USR}@10.1.0.5:/home/Saikumar/'
            }
        }
    }
}
