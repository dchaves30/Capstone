pipeline {
  agent any
  stages {
    stage('Upload') {
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