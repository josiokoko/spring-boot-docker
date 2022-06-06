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
        withCredentials([usernamePassword(credentialsId: 'josiokoko', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUsername')]) {
          sh "docker login -u ${env.dockerHubUsername} -p ${env.dockerHubPassword}"
        }
        sh "docker push -t josiokoko/spring-boot-mongo"
      }
    }
    
  }
}
  
