pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }
  


stages {
      stage("code from github"){
          steps{
            git branch: 'master', url: 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
          
          }
      }
      stage("build the code")
	{
          steps{
              sh "mvn clean package"
          }
      }
      



	stage("deploy the code"){
          steps{
             deploy adapters: [tomcat9(credentialsId: '1011', path: '', url: 'http://43.204.149.82:8080/')], contextPath: 'bhupesh', war: '**/*.war'
          }
      }
  }
}
