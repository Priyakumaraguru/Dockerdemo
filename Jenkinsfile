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
          sh "docker run --name nginx -itd -p 8082:80 docker:latest"   
        }  
      }
      stage("Pushing to docker hub"){
        steps{
        
            sh "docker commit nginx priya4/docker:latest"
            sh "docker push priya4/docker:latest"   
          
        }  
      }
   }
}


