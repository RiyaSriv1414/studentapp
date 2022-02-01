pipeline {
    agent any
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
        stage('Push Docker Image') {
              steps {
                 withCredentials([usernameColonPassword(credentialsId: 'dockerhub', variable: 'dockerpwd')]) {
                 // some block
                      bat "docker login -u riyasriv -p ${dockerpwd}"
                  }
                      bat "docker push riyasriv/imagefirst:${BUILD_NUMBER}"
              }
          }
    }
}
