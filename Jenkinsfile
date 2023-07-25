pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('SonarQube') {
      steps {
        sh './mvnw clean verify sonar:sonar -Dsonar.host.url=https://172.17.0.1:9000'
      }
    }

    stage('Execute') {
      steps {
        sh 'java -jar target/*.jar --server.port=8082'
      }
    }

  }
}