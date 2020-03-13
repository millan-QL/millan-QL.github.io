pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        sh 'commitChangeset = sh(returnStdout: true, script: \'git diff-tree --no-commit-id --name-status -r HEAD\').trim()'
      }
    }

  }
}