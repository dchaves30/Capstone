pipeline {
  agent any
  stages {
    stage('Begin') {
      steps {
        echo 'Hello'
      }
    }

    stage('Test') {
      steps {
        sh 'tidy -q -e test.html'
      }
    }

  }
}