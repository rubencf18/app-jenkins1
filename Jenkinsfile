pipeline {
  agent any
  stages {
    stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
    stage('Build') {
      steps {
        sh 'docker run -rm -u root build -t app .'
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
