pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        fileExists 'core-40.json'
      }
    }

    stage('Send Email') {
      steps {
        emailext(subject: 'test mail', body: 'Build Logs', attachLog: true, compressLog: true, from: 'nikhita@biconomy.io', to: 'nikhita@biconomy.io')
      }
    }

  }
}