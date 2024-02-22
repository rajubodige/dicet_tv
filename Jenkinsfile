pipeline {
    agent any

    stages {
        stage('code from github') {
            steps {
                git 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
            }
        }
        stage('Build the code') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'greatcoder', path: '', url: 'http://13.127.190.216:8080/')], contextPath: 'bhupesh', war: '**/*.war'
            }
        }
    }
}
