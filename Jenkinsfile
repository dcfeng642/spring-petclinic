pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        sh 'git clone https://github.com/dcfeng642/spring-petclinic.git'
      }
    }
    
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
