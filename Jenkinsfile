pipeline {
  environment {
     FOO = "Testing ENV variable"
     ENV_NAME = "${env.BRANCH_NAME}"
     LOG = "LOG"
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
          LOG = `git log -3 --format="Details :  %ad -by- %an, --: Change :--  %s "  --date=relative`
          echo "Running LOG ${LOG} now"
          env.custom_var = LOG
        }
      }

      stage('Step 3') {
      steps {
        
        slackSend color: '#BADA55', message: "[${env.ENV_NAME}] -- Just testing ~ ENV_NAME!" 
        slackSend color: '#BADA55', message: "[${env.LOG}] -- Just testing ~ LOG" 
        slackSend color: '#BADA55', message: "[${env.FOO}] -- Just testing ~ FOO!!" 
        }
      }
    }
}