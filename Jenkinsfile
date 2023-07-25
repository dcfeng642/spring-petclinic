pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Execute') {
      steps {
        sh 'java -jar target/*.jar --server.port=8083'
      }
    }

  }
}