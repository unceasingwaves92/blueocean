pipeline {
  agent any
  stages {
    stage('Development Build') {
      steps {
        echo 'Pull code from GitHub repository'
        echo 'Create a build using repo'
      }
    }

    stage('Smoke Test') {
      steps {
        echo 'Run 2 Smoke Tests'
      }
    }

    stage('Deploy in QA') {
      steps {
        echo 'Stop the Server'
        echo 'Move the build in QA environment'
        echo 'Start the server'
        echo 'Notify to QA by email'
      }
    }

    stage('Integration Testing') {
      parallel {
        stage('Integration Testing') {
          steps {
            echo 'Sanity Test UI'
          }
        }

        stage('API Test') {
          steps {
            echo 'Run REST Automation'
          }
        }

        stage('Performance Test') {
          steps {
            echo 'Run Jmeter Tests'
          }
        }

      }
    }

    stage('Certify') {
      steps {
        echo 'QA Team Certify'
      }
    }

  }
}