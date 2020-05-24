pipeline {
  agent any
  stages {
    stage('Echo Build Async Solution') {
            steps {
        bat 'echo start build of sln'
      }
    }
    stage('Build Async Solution') {
      steps {
        bat(script: 'echo second step', returnStatus: true, returnStdout: true)
      }
    }
  }
}
