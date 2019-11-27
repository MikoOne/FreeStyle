pipeline {
  agent any
  stages {
    stage('pre-build') {
      steps {
        sh 'pod install'
        echo 'AAA'
      }
      steps{
        echo 'BB'
      }
    }

    stage('build') {
      steps {
        sh '''xcodebuild -workspace JenkinsFreeStyle.xcworkspace -scheme JenkinsFreeStyle clean build
'''
      }
    }

    stage('test') {
      steps {
        sh 'xcodebuild test -workspace JenkinsFreeStyle.xcworkspace -scheme JenkinsFreeStyle  -destination \'platform=iOS Simulator,name=iPhone 11\''
      }
    }

  }
}