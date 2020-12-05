pipeline {
  agent any 
    stages{
      stage("Docker Build"){
        steps{
          sh "docker build -t docker ."   
        }  
      }
      stage("Run Docker image"){
        steps{
          sh "docker run -itd -p 8082:80 docker"   
        }  
      }
      stage("Pushing to docker hub"){
        steps{
          withCredentials([usernamePassword(credentialsId: 'dockerhub_priya', passwordVariable: 'pass', usernameVariable: 'userId')]) {
          sh "docker push priya4/docker:latest"   
          }
        }  
      }
   }
}


