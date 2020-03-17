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

    stage('notify on slack STEP 3') {
      steps {
        script {
          slackSend(message: "Hello test", channel: '#T0F3F1QMB', color: 'good', failOnError: true, teamDomain: 'BV8NATMB3', token: 'cXSJNOLxqqp69CO8K2TDHEWQ')
        }

      }
    }

  }
}