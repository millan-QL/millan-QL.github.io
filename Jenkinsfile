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
        sh '''shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:\'%h\'").trim()

echo "" 
echo shortCommit
echo " " 
echo "shortCommit" 
echo " " 
echo $(shortCommit)
echo " " 
echo $shortCommit'''
      }
    }

  }
}