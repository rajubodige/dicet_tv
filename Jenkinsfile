pipeline {
    agent any

    stages {
        stage('code from github') {
            steps {
                git 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
            }
        }
        stage('build project') {
            steps {
                sh "mvn clean package"
            }
        }
        stage('deploy project') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'pipelinetomcat', path: '', url: 'http://34.212.183.191:8081/')], contextPath: 'bhupesh', war: '**/*.war'
            }
        }
    }
}
