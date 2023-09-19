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
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.111.150.200:8080/')], contextPath: 'newproject', war: '**/*.war'
            }
        }
    }
}
