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
        sh '''def getChangeString() {
MAX_MSG_LEN = 100
def changeString = ""

echo "Gathering SCM changes"
def changeLogSets = currentBuild.rawBuild.changeSets
for (int i = 0; i < changeLogSets.size(); i++) {
def entries = changeLogSets[i].items
for (int j = 0; j < entries.length; j++) {
def entry = entries[j]
truncated_msg = entry.msg.take(MAX_MSG_LEN)
changeString += " - ${truncated_msg} [${entry.author}]\\n"
}
}

if (!changeString) {
changeString = " - No new changes"
}
return changeString
}'''
        }
      }

    }
  }