pipeline {
  agent any
  stages {
    stage('Stage 1') {
            steps {
        bat 'echo start build of sln'
      }
    }
    stage('Stage 2') {
      steps {
        bat 'echo Second Step'
        /*bat "\"${tool 'Default MS Build'}\" \"C:\\Program Files (x86)\\Jenkins\\workspace\\JenkinsPipeAsCode_master\\AdvancedAsyncSourceCode\\AdvancedAsyncDemo.sln\" /p:Configuration=Release /p:Platform=\"Any CPU\" /p:WarningLevel=2;OutDir=\"C:\\Siddharth\\PublishAsyncSourceCode\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"*/
      }
    }
  }
}
