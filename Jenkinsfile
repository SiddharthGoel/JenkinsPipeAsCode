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
        bat 'echo Second Step'
        bat "\"${tool 'MSBuild'}\" \"C:\\Program Files (x86)\\Jenkins\workspace\JenkinsPipeAsCode_master\AdvancedAsyncSourceCode\AdvancedAsyncDemo.sln\" /p:Configuration=Release /p:Platform=\"Any CPU\" /p:WarningLevel=2;OutDir=\"C:\Siddharth\PublishAsyncSourceCode\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
      }
    }
  }
}
