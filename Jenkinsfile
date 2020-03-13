pipeline {
  agent any
  stages {
    stage('Step 1') {
      steps {
        sh 'echo "hello"'
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