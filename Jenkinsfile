pipeline {
    agent any

    stages {
        stage('GET THE CODE FROM GITHUB') {
            steps {
                git 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
            }
        }
        
        stage('BUILD THE CODE') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('DEPLOYMENT') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'pipeline', path: '', url: 'http://65.2.143.169:8080/')], contextPath: 'bhupesh', war: '**/*.war'
            }
        }
        
        
        
    }
}
