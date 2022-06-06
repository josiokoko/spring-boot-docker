pipeline {
  agent any
  stages {
    
    stage("SCM Clone"){
      steps{
        git credentialsId: 'jenkinsGit', url: 'https://github.com/josiokoko/spring-boot-docker.git'
      }
    }
    
    stage("Maven Build"){
      steps{
        sh 'mvn clean package'
      }
    }
    
  }
}
  
