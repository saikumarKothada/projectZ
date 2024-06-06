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

        stage('Push to Test') {
            when {
                branch 'test' // Only run this stage on the 'test' branch
            }
            steps {
                // Add steps to copy Git files to the test server
                sh "rsync -avz ${WORKSPACE}/push-to-test ${TEST_SERVER_CREDENTIAL_USR}@10.1.0.5:/home/Saikumar"
            }
        }

        stage('Push to Prod') {
            when {
                branch 'prod' // Only run this stage on the 'master' branch
            }
            steps {
                // Add steps to copy Git files to the prod server
                sh "rsync -avz ${WORKSPACE}/push-to-prod ${TEST_SERVER_CREDENTIAL_USR}@10.1.0.6:/home/Saikumar"
            }
        }
    }
}
