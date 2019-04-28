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
        sh 'docker run -rm --name app -id -p 80:80 app:test'
        sh '/bin/nc -vc localhost 80'
      }
      post {
        always {
          sh 'docker container stop app'
        }
      }
    }
    stage('Push Registry'){
      steps {
        sh 'docker tag app:test rubencf18/app:stable'
        sh 'docker push rubencf18/app:stable'
      }
    }
  }
}
