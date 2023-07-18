pipeline {
    agent any
    stages {
        stage ('SCM') {
            steps {
                git branch: 'master', url: 'https://github.com/kvchiru/dicet_tv.git'
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://52.66.208.77:8080/')], contextPath: 'direct', war: '**/*.war'
            }
        }
    }
}
