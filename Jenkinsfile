pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }
  stages {
      stage("get the code from git")
	{
          steps{
            git branch: 'master', url: 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
          
          }
      }
      stage("build"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy"){
          steps{
             deploy adapters: [tomcat9(credentialsId: 'pipeline', path: '', url: 'http://3.110.170.200:8080/')], contextPath: 'Thiru', war: '**/*.war'
          }
      }
  }
}
