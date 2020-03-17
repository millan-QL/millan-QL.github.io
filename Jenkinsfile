pipeline {
  agent any
  stages {
    stage('Step 1') {
      steps {
        sh '''echo "  ++++++++++  "
LOG=`git show :/^Merge --pretty="format:%an %ar %s"`
echo $LOG
echo "  ++++++++++  "'''
      }
    }

  }
}