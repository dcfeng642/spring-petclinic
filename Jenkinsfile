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
            sh 'sh "/var/jenkins_home/sonar-scanner/sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner -Dsonar.host.url=https://172.17.0.1:9000 -Dsonar.projectName=meanstackapp -Dsonar.projectVersion=1.0 -Dsonar.projectKey=meanstack:app -Dsonar.sources=. "'
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