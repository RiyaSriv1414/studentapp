pipeline {
    agent any
    environment{
        PATH = "C:\Program Files\ApacheMaven\apache-maven-3.8.4\bin:$PATH"
    }
    stages {
        stage('Git SCM checkout') {
            steps {
                git branch: 'main', credentialsId: 'Mycred', url: 'https://github.com/RiyaSriv1414/studentapp.git'
            }
        }
        stage('MVN package Build') {
            steps {
                sh "mvn clean install"
            }
        }
    }
}
