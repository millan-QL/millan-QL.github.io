pipeline {
  environment {
     FOO = "Testing ENV variable"
     ENV_NAME = "${env.BRANCH_NAME}"
     LOG = "LOG_env"
     LOG_NEW = gitLog()
     CUST_VAR = "test"
     CUST_VAR_2 = "test_2"
   }
  

agent any
  stages {

    stage('Step 1') {
      steps {
        sh "echo ${FOO}"
        echo 'Building Environment: ' + ENV_NAME
        sh 'echo "THIS IS STEP 1"'
      }
    }

    stage('Step 2') {
      steps {
        script {
        echo "THIS IS STEP 2"
          LOG = git log -3 --format Details %ad %an %s --date=relative
          echo "Running LOG ${LOG} now"
          CUST_VAR = $(LOG)
          CUST_VAR_2 = LOG
        }
      }
    }

    def gitLog() {
       return env.LOG_NEW
}

    stage('Step 3') {
      steps {
        slackSend color: '#BADA55', message: "[${env.LOG_NEW}] -- Just testing ~ LOG_NEW" 
        
        }
      }
}
}