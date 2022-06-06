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
        sh 'maven3.6.3/bin/mvn clean package'
      }
    }
    
  }
}
  
