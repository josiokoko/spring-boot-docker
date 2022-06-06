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
    
    stage("SonarQube Report"){
      steps{
        sh 'mvn sonar:sonar'
      }
    }
    
    stage("Docker Build"){
      steps{
        sh "docker build -t josiokoko/spring-boot-mongo ."
      }
    }
    
  }
}
  
