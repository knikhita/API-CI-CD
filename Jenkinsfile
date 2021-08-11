pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        fileExists 'core-40.json'
      }
    }

    stage('Report') {
      steps {
        sh '''publishHTML(target: [
            allowMissing: false,
            alwaysLinkToLastBuild: false,
            keepAll: true,
            reportDir: \'coverage\',
            reportFiles: \'index.html\',
            reportTitles: "SimpleCov Report",
            reportName: "SimpleCov Report"
          ])'''
        }
      }

      stage('Send mail') {
        steps {
          emailext(subject: 'API test mail', body: 'PLease download the HTML report', attachLog: true, compressLog: true, from: 'nikhita@biconomy.io', to: 'nikhita@biconomy.io')
        }
      }

    }
  }