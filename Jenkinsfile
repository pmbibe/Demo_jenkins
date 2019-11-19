//HelloWorld
pipeline {
  agent any
  
  stages {
    stage('Prepare') {
      steps {
        echo "--------------------Prepare Stage---------------------"
        sh "rm -rf Demo_jenkins"
        sh "https://github.com/pmbibe/Demo_jenkins"
        sh "phpunit --version"
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
        sh "pwd"
        junit 'Demo_jenkins/build/logs/*.xml'
        
      }
    }
  }
}
