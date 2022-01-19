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
                sh 'mvn clean package'
            }
        }
    }
}
