pipeline {
  options {
    disableConcurrentBuilds()
  }

  agent {
    label "katalon-studio"
  }

  stages {
    stage('Running test') {
      steps {
        container('katalon') {
            sh 'katalon-execute.sh -browserType="Chrome" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/TS_RegressionTest"'
        }
      }
    }
  }
}