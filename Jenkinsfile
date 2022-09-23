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
               withSonarQubeEnv(installationName: 'sonarserver', credentialsId: 'sonarpost-token') {
                bat 'mvn clean package sonar:sonar'
                }
            }
        }
  }
}
