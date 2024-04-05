pipeline {
  agent any
  stages {
    stage('Build') {
      environment {
        SCANNER_HOME = tool 'sonaqube_scanner'
      }
      steps {
        withMaven() {
          sh './mvnw package'
        }
        withSonarQubeEnv(installationName: 'my_sonarqube') {
          sh '$SCANNER_HOME/bin/sonar-scanner \
         -Dsonar.projectKey=spring-petclinic \
         -Dsonar.projectName=spring-petclinic \
         -Dsonar.sources=target/ '
        }
      }
    }

  }
}
