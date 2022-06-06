pipeline {
  agent any
  tools {
    maven 'maven3.6.3' 
  }
  environment {
		DOCKERHUB_CREDENTIALS=credentials('josiokoko')
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
	sh "docker tag josiokoko/spring-boot-mongo:latest josiokoko/java-webapp-mongo:v1
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                		
	echo 'Login Completed'
        sh "docker push josiokoko/java-webapp-mongo:v1"
      }
    }
    
  }
}
  
