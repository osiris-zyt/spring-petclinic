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
          sh '$SCANNER_HOME/bin/sonar-scanner -Dsonar.projectKey=petclinic              -Dsonar.projectName=petclinic              -Dsonar.token=sqa_c2911b564f9d8e7b01fe05e4f8d6ca475ed982c2'
        }

      }
    }

  }
}