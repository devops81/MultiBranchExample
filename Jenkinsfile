pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        sh 'echo "This is checkout space"'
      }
    }

    stage('Build') {
      steps {
        sh 'echo "This is build step"'
      }
    }

    stage('Notify') {
      steps {
        sh 'echo "This is build notfication step"'
      }
    }

  }
}