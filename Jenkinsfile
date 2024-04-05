pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        withMaven() {
          sh './mvnw package'
          sh './mvnw spring-boot:run'
        }

      }
    }

  }
}