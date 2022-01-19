pipeline {
    agent any

    stages {
        stage('Git SCM checkout') {
            steps {
                git credentialsId: 'Git', url: 'https://github.com/RiyaSriv1414/my-app.git'
            }
        }
        stage('MVN package Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
