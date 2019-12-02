pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/devops81/MultiBranchExample.git']]])
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
