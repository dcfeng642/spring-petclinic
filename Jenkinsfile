pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh './mvnw package'
          }
        }

        stage('SonarQube Analysis') {
          steps {
            sh './mvnw clean verify sonar:sonar'
          }
        }

      }
    }

    stage('Execute') {
      steps {
        sh 'java -jar target/*.jar --server.port=8082'
      }
    }

  }
}