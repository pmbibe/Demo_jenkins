//HelloWorld
pipeline {
  agent any
  
  stages {
    stage('Prepare') {
      steps {
        echo "--------------------Prepare Stage---------------------"
        sh "rm -rf Demo_jenkins"
        sh "git clone https://github.com/pmbibe/Demo_jenkins"
        sh "chmod -R 755 Demo_jenkins"
      }
    }
    stage('Test') {
      steps {
        echo "--------------------Test Stage---------------------"
        sh "cd Demo_jenkins && pwd && ant"
      }
    }
    stage('Deploy') {
      steps {
        echo "--------------------Deploy Stage---------------------"
        junit 'Demo_jenkins/build/logs/*.xml'
        sh "./Deploy.sh"
        
      }
    }
  }
}
