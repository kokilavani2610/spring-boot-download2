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
               withSonarQubeEnv(installationName: 'ProductionSonarQube scanner', credentialsId: 'SonarQubetoken') {
                bat '''                 
                mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar
                mvn clean package sonar:sonar
                '''
                }
            }
        }
  }
}
