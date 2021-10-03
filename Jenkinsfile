pipeline {
  agent any
  stages {
    stage('Dev Code Pull ') {
      steps {
        echo 'Pull the Code from DEV'
      }
    }

    stage('Dev Maven Build') {
      steps {
        echo 'Build the Dev Code thru Maven'
      }
    }

    stage('QA Deploy') {
      steps {
        echo 'Deploy the Code for QA'
      }
    }

    stage('QA Tests') {
      parallel {
        stage('QA Tests') {
          steps {
            echo 'Web (Code Pull, Run tests)'
          }
        }

        stage('Web (Code Pull, Run tests)') {
          steps {
            echo 'Web (Code Pull, Run tests)'
          }
        }

        stage('API (Code Pull, Run tests)') {
          steps {
            echo 'API (Code Pull, Run tests)'
          }
        }

      }
    }

    stage('QA Certification') {
      steps {
        input 'QA Completed'
      }
    }

    stage('UAT Deploy') {
      steps {
        echo 'Deploy for UAT'
      }
    }

    stage('UAT Certification') {
      steps {
        echo 'UAT Certification'
        input 'UAT Completed'
      }
    }

    stage('Prod Deploy') {
      steps {
        echo 'Deploy in Prod'
      }
    }

  }
}