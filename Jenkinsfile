pipeline {
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
LOG=`git log -3 --format="Details :  %ad -by- %an, --: Change :--  %s  "  --date=relative`
echo $LOG'''
      }
    }


    stage("speak") {
        slackSend color: '#BADA55', message: 'Just testing ~ Hello, World!'
    }

  }
}