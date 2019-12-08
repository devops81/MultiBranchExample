rtMaven.tool = 'Maven3'
pipeline {
  agent any
  {
    jdk "JAVA8"
    maven "Maven3"
  }
  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/devops81/MultiBranchExample.git']]])
      }
    }

    stage('Build') {
      steps {
        script {
        rtMaven.run pom: 'pom.xml',goals: 'clean package' 
        }
      }
    }

    stage('Notify') {
      steps {
        sh 'echo "This is build notfication step"'
      }
    }

  }
}
