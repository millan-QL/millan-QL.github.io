pipeline {
  agent any
  stages {
    stage('Step 1') {
      steps {
        sh '''echo "hello"
shortCommit=\'sh(returnStdout: true, script: "git log -n 1 --pretty=format:\'%h\'").trim()\'
echo $shortCommit'''
      }
    }

  }
}