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
git log -3 --format="%h -:- %ad -:- %an, --:- Change -:--  %s  "  --date=relative'''
      }
    }

  }
}