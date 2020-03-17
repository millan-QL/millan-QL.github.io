pipeline {
  agent any
  parameters {
            string(name: 'custom_var', defaultValue: '')
        }

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
echo $'''
env.custom_var = LOG
              }
      }
    }


    stage('Step 3') {
      steps {
        slackSend color: '#BADA55', message: "[${env.custom_var}] -- Just testing ~ Hello, World!" 
      }
    }

  }
}