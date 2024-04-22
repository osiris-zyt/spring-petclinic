pipeline {
  agent any
  stages {
    stage('Build') {
      environment {
        SCANNER_HOME = tool'sonaqube_scanner'
      }
      steps {
        withMaven() {
          sh './mvnw package'
        }

      }
    }
    stage('Deploy') {
            steps {
                ansiblePlaybook playbook: 'deploy.yaml'
                
            }
        }

  }
}
