pipeline {
  agent any
  stages {
    stage('Print') {
      steps {
        script {
          echo 'test'          
        }
      }
    }
    stage ('Scan') {
            steps {
               withSonarQubeEnv(installationName: 'sonarqubeserver', credentialsId: 'sonartoken') {
                bat 'mvn --version'
                }
            }
        }
  }
}
