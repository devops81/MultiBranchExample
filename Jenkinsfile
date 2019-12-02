pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        sh 'ECHO "This is checkout space"'
      }
    }

    stage('Build') {
      steps {
        sh 'This is build step'
      }
    }

    stage('Notify') {
      steps {
        emailext(subject: 'Newbuild', body: 'Newbuild', attachLog: true)
      }
    }

  }
}