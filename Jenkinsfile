pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker -v build -t app:test .'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
        sh 'docker run -d --name app app:test'
        sh 'nc -vz localhost 80'
        sh 'docker stop app'
      }
    }
    stage('Push Registry'){
      steps {
        sh 'docker tag app:test rcamacho/app:stable'
        sh 'docker push rcamacho/app:stable'
      }
    }
  }
}
