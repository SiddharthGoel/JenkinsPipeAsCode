pipeline {
  agent any
  stages {
    stage('Echo Build Async Solution') {
      agent {
        node {
          label 'Primary'
        }

      }
      steps {
        bat(returnStatus: true, returnStdout: true, script: 'echo start build of sln', label: 'Echo Build Start')
      }
    }

    stage('Build Async Solution') {
      agent {
        node {
          label 'Second'
        }

      }
      steps {
        bat(script: 'echo second step', returnStatus: true, returnStdout: true)
      }
    }

  }
  environment {
    Primary = 'master'
    Second = 'master'
  }
}