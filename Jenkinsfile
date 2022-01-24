pipeline {
    agent any
    environment {
    registryCredential = 'dockerhub'
    }
    stages {
        stage('Git SCM checkout') {
            steps {
                git branch: 'main', credentialsId: 'Mycred', url: 'https://github.com/RiyaSriv1414/studentapp.git'
            }
        }
        stage('MVN package Build') {
            steps {
                bat "mvn clean install"
            }
        }
        stage('Build Docker Image') {
              steps {
                  bat "docker build -t riyasriv/imagefirst:${BUILD_NUMBER} ."
              }
          }
    }
}
