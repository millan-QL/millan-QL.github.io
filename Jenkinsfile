pipeline {
  environment {
     ENV_NAME = "${env.BRANCH_NAME}"
     LOG_NEW = "LOG_env"
   }
  agent any
  stages {
    stage('Step 1') {
      steps {
        sh 'echo "THIS IS STEP 1"'
      }
    }

    stage('Step 2') {
      steps {
        sh '''echo "THIS IS STEP 2"
        LOG="git log -3 --format %ad -by- %an  %s  --date=relative"
        echo ${LOG}'''
        slackSend color: '#BADA55', message: 'Hello, World! [${LOG}] and [${env.LOG}] - [${env.ENV_NAME}] -- [${env.LOG_NEW}]'
      }
    }

  }
}