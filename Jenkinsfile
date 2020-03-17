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

    stage('') {
      steps {
        slackSend(failOnError: true, botUser: true, message: '$LOG', baseUrl: 'https://hooks.slack.com/services/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')
        echo 'THIS IS STEP 3'
      }
    }

  }
}