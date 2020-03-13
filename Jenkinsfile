pipeline {
  agent any
  stages {
    stage('Step 1') {
      steps {
        sh '''echo "hello"
shortCommit=`sh(returnStdout: true, script: "git log -n 1 --pretty=format:\'%h\'").trim()\'
echo $shortCommit'''
      }
    }

    stage('Step 2') {
      steps {
        echo 'Hello I am here'
        sh '''MY_MESSAGE="Hello World"
echo $MY_MESSAGE'''
      }
    }

  }
}