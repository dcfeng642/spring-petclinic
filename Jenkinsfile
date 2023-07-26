pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Deploy') {
      steps {
        sh 'java -jar target/*.jar --server.port=8082'
      }
    }

  }
}
