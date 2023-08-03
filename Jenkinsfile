pipeline {
  agent any
  stages {
    stage('Git clone') {
      steps {
        git(
          url: "https://github.com/spring-projects/spring-petclinic.git",
          branch: "main"
        )
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
