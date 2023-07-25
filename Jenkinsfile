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
            sh 'sh /var/jenkins_home/sonar-scanner/sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner'
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