pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        fileExists 'core-40.json'
      }
    }

    stage('End : Send Email') {
      steps {
        emailext(subject: 'API test mail', body: 'PLease download the HTML report', attachLog: true, compressLog: true, from: 'nikhita@biconomy.io', to: 'nikhita@biconomy.io')
      }
    }

  }
}