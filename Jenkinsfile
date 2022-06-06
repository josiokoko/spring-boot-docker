pipeline {
  agent any
  tools {
    maven 'maven3.6.3' 
  }
  stages {
    
    stage("Maven Build"){
      steps{
        sh 'mvn clean package'
      }
    }
    
    
    stage("Docker Build"){
      steps{
        sh "docker build -t josiokoko/spring-boot-mongo ."
      }
    }
    
    stage("Push Image to Registry"){
      steps{
        withCredentials([string(credentialsId: 'DockerHubCredentialLatest', variable: 'DockerHubCredentialLatest')]) {
          sh "docker login -u josiokoko -p ${DockerHubCredentialLatest}"
        }
        sh "docker push -t josiokoko/spring-boot-mongo"
      }
    }
    
  }
}
  
