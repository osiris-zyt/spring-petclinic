pipeline {
  agent any
  stages {
    stage('Build') {
      environment {
        SCANNER_HOME = 'sonaqube_scanner'
      }
      steps {
        withMaven() {
          sh './mvnw package'
        }

        withSonarQubeEnv('my_sonarqube') {
          sh '$SCANNER_HOME/bin/sonar-scanner          -Dsonar.projectKey=spring-petclinic          -Dsonar.projectName=spring-petclinic          -Dsonar.sources=target/ '
        }

      }
    }

  }
}