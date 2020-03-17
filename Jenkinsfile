pipeline {
  agent any
  stages {
    stage('Step 1') {
      steps {
        sh '''echo "  --------  "
echo " "
LOG=`git log --oneline --decorate`
echo $LOG
echo "  --------  "'''
      }
    }

  }
}