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
      sh "docker build -t josiokoko/spring-boot-mongo ."
    }
    
  }
}
  
