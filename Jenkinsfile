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
        git(changelog: true, poll: true, url: 'git@github.com:millan-QL/millan-QL.github.io.git')
      }
    }

  }
}