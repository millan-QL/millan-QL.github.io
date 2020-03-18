pipeline {
  environment {
     ENV_NAME = "${env.BRANCH_NAME}"
     LOG_NEW = "LOG_env"
   }
  agent any
  stages {

    stage('build') {
      steps {
        script {
          awesomeVersion = sh(returnStdout: true, script: 'echo 0.0.1')
        }
      }
    }

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
      }
    }

    stage('Step 3') {
      steps {
        sh 'echo "THIS IS STEP 3"'
        slackSend color: '#BADA55', message: 'Hello, World! [${LOG}] and [${env.BRANCH_NAME}] - [${ENV_NAME}] -- [${LOG_NEW}]. and [${LOG}]'
      }
    }

    stage('output_version') {
      steps {
        echo "awesomeVersion: ${awesomeVersion}"
      }
    }

  }
}