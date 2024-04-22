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

      }
    }

    stage('Deploy') {
      steps {
        ansiblePlaybook 'deploy.yaml'
      }
    }

  }
}