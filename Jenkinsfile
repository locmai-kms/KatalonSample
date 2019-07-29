pipeline {
  options {
    disableConcurrentBuilds()
  }

  agent {
    label "katalon-studio"
  }

  stages {
    stage('Run Tests') {
      parallel {
          stage('Chrome') {
            steps {
                container('katalon-chrome') {
                    sh 'katalon-execute.sh -browserType="Chrome" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/TS_RegressionTest"'
                }
            }
          }
          stage('Firefox') {
            steps {
              container('katalon-firefox') {
                sh 'katalon-execute.sh -browserType="Firefox" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/TS_RegressionTest"'
              }
            } 
          }
      }
    }
  }
}