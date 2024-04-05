pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        withMaven() {
          sh './mvnw package'
        }

      }
    }

  }
}