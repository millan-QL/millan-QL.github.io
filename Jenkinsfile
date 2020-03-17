pipeline {
  agent any
  stages {
    stage('Step 1') {
      steps {
        sh '''echo "hello"
shortCommit=\'sh(returnStdout: true, script: "git log -n 1 --pretty=format:\'%h\'").trim()\'
echo $shortCommit'''
        sh '''echo " "
echo " ************. "
echo " "
LOG=`git log --graph --pretty=format:\'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset\' --abbrev-commit`
echo $LOG
echo " "



'''
      }
    }

  }
}