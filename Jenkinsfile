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

        withSonarQubeEnv(installationName: 'my_sonarqube', credentialsId: '82eb34fe-ee23-4cf8-a395-e011982a10c1') {
          sh '$SCANNER_HOME/bin/sonar-scanner '
        }

      }
    }

  }
}