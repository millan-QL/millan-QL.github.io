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
        sh '''script 
{
	env.CHANGESET = sh (
	
		script: "cm status --cset | grep -o -E \'[0-9]+\' | head -1 | sed -e \'s/^0\\\\+//\'",
		returnStdout: true,
		label: "Retrieving changeset id"
	)
}'''
      }
    }

  }
}