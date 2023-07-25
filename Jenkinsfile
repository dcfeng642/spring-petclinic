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
            sh 'sh "/home/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarQubeScanner/bin/sonar-scanner -Dsonar.host.url=http://172.17.0.1:9000 -Dsonar.projectName=meanstackapp -Dsonar.projectVersion=1.0 -Dsonar.projectKey=meanstack:app -Dsonar.sources=. -Dsonar.projectBaseDir=/home/jenkins/workspace/sonarqube_test_pipeline"'
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