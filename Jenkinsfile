pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Ansible') {
      steps {
        sh 'ansible-playbook -i hosts site.yml'
      }
    }

  }
}
