pipeline {
  agent any
  stages {
    stage('Echo Build Async Solution') {
            steps {
        ECHO ON
        bat 'echo start build of sln'
        echo first step
      }
    }
    stage('Build Async Solution') {
      steps {
        bat(script: 'echo second step', returnStatus: true, returnStdout: true)
        echo first step
      }
    }
  }
}
