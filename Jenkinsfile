pipeline {
    agent any
    stages {


stage('Build the MVN project')
{
    steps {
        script {
def mvnHome = tool name: 'MavenHome', type: 'maven'
            sh "${mvnHome}/bin/mvn package" }
    }
}
stage('Build Docker Image')
{
    steps {
sh 'docker build -t devops81/my-app:2.1.2 .'
    }
}
 stage('Push Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker_hub_login') {
                        app.push("${env.BUILD_NUMBER}")
                        app.push("latest")
                    }
                }
            }
        }

    }
}
