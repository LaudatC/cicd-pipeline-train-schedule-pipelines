pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        echo 'Running Build Automation'
        sh './gradlew build --no-daemon'
        archiveArtifatcs artifacts: 'dist/trainSchedule.zip'
      }
    }
  }
}
