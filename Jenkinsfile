pipeline {
  agent any
  stages {
    stage('pre-build') {
      steps {
        sh 'pod install'
      }
    }

    stage('build') {
      steps {
        sh 'xcodebuild test -workspace JenkinsFreeStyle.xcworkspace -scheme JenkinsFreeStyle  -destination \'platform=Simulator,name=iPhone 11,OS=13.1\''
      }
    }

    stage('test') {
      steps {
        sh 'xcodebuild test -workspace JenkinsFreeStyle.xcworkspace -scheme JenkinsFreeStyle  -destination \'platform=iOS Simulator,name=iPhone 11\''
      }
    }

  }
}