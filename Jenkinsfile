pipeline {
    agent any
    stages {
        stage('etlJobScriptWrapper_copy_dropbox_csvsPhase') {
            steps {
                build 'etlJobScriptWrapper_copy_dropbox_csvs'
            }
        }
        stage('etlJobCalcVerifyDataPreRunPhase') {
            steps {
                build 'etlJobCalcVerifyDataPreRun'
            }
        }
        stage('etlJobCopyTablesFromAWSPhase') {
            steps {
                build 'etlJobCopyTablesFromAWS'
            }
        }
    }
}