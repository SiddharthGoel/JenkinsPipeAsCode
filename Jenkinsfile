pipeline {
  agent any
  stages {
    stage('Stage 1') {
            steps {
        bat 'echo Stage 1'
      }
    }
    stage('Stage 2') {
      steps {
        bat 'echo Stage 2 Webhook another try'
        bat 'exit 9'
        /*bat "\"${tool 'Default MS Build'}\" \"C:\\Program Files (x86)\\Jenkins\\workspace\\JenkinsPipeAsCode_master\\AdvancedAsyncSourceCode\\AdvancedAsyncDemo.sln\" /p:Configuration=Release /p:Platform=\"Any CPU\" /p:WarningLevel=2;OutDir=\"C:\\Siddharth\\PublishAsyncSourceCode\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"*/
      }
    }
  }
  post {
        always {
  emailext body: '''$PROJECT_NAME - Build # $BUILD_NUMBER - $BUILD_STATUS:

Check console output at $BUILD_URL to view the results.

$BUILD_LOG''', recipientProviders: [developers(), culprits(), brokenBuildSuspects(), upstreamDevelopers()], subject: '$PROJECT_NAME - Build # $BUILD_NUMBER - $BUILD_STATUS!', to: 'sidd456goel@hotmail.com'
}
    }          
}
