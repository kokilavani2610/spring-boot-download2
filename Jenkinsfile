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
                bat '''
                mvn --version
                mvn clean verify sonar:sonar -Dsonar.login=SonarQubetoken
                mvn clean install
                mvn sonarqube -Dsonar.branch.name=main
                mvn sonar:sonar -Dsonar.login=myAuthenticationToken
                '''
                }
            }
        }
  }
}
