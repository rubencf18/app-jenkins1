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
        sh 'docker run -it app'
        sh 'nc -vc localhost 80'
        sh 'docker stop app'
      }
    }
    stage('Push Registry'){
      steps {
        sh 'docker tag app rubencf18/app:stable'
        sh 'docker push rubencf18/app:stable'
      }
    }
  }
}
