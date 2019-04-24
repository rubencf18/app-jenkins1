pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker -v build -t app .'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
      }
    }
    stage('Deploy'){
      steps {
        echo 'DEPLOY'
      }
    }
  }
}
