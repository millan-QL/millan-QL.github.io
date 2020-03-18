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
        LOG="git log -3 --format %ad -by- %an  %s  --date=relative"
        echo ${LOG}'''
      }
    }

  }
}