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
        bat 'echo Stage 2 Webhook another try $PROJECT_NAME - Build # $BUILD_NUMBER '
        print "BRANCH: ${env.BRANCH_NAME}, COMMIT: ${env.GIT_COMMIT}"
        print "CHANGE_AUTHOR_DISPLAY_NAME: ${env.CHANGE_AUTHOR_DISPLAY_NAME}, CHANGE_AUTHOR_EMAIL: ${env.CHANGE_AUTHOR_EMAIL}, CHANGE_AUTHOR : ${env.CHANGE_AUTHOR}"
        bat 'ECHO CHANGE_AUTHOR_DISPLAY_NAME $CHANGE_AUTHOR_DISPLAY_NAME    ECHO CHANGE_AUTHOR_EMAIL $CHANGE_AUTHOR_EMAIL       ECHO CHANGE_AUTHOR $CHANGE_AUTHOR ECHO '
        /*bat 'exit 9'*/
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
