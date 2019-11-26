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
        sh 'xcodebuild test -workspace JenkinsFreeStyle.xcworkspace -scheme JenkinsFreeStyle  -destination \'platform=iOS Simulator,name=iPhone 11\''
      }
    }

    stage('test') {
      steps {
        sh 'xcodebuild test -workspace ${WORKSPACE}.xcworkspace -scheme ${SCHEME}  -destination \'platform=iOS Simulator,name=iPhone 11\''
      }
    }

  }
}