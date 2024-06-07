pipeline {
    agent {
        label 'j-slave'
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

        stage('Copy to Test Node') {
            steps {
                // Copy files to the test node
                sh 'sshpass -p ${TEST_SERVER_CREDENTIAL_PSW} scp -r ${WORKSPACE} ${TEST_SERVER_CREDENTIAL_USR}@10.1.0.5:/home/Saikumar/'
            }
        }

        stage('Run Prod Job') {
            when {
                expression { currentBuild.resultIsBetterOrEqualTo('SUCCESS') }
            }
            steps {
                // Copy files to the prod node 
                sh 'sshpass -p ${TEST_SERVER_CREDENTIAL_PSW} scp -r ${WORKSPACE} ${TEST_SERVER_CREDENTIAL_USR}@10.1.0.6:/home/Saikumar/'
            }
        }
    }
}
