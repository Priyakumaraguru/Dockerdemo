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
          sh "docker run --name nginx -itd -p 8082:80 docker"   
        }  
      }
      stage("Pushing to docker hub"){
        steps{
          withCredentials([usernamePassword(credentialsId: 'dockerhub_priya', passwordVariable: 'pass', usernameVariable: 'userId')]) {
            sh "docker commit nginx '${userId}'/docker:latest"
            sh "docker push '${userId}'/docker:latest"   
          }
        }  
      }
   }
}


