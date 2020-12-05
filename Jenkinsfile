pipeline {
  agent any 
    stages{
      stage("Docker Build"){
        steps{
          sh 'ubuntu@172.31.36.52 \"docker build -t docker .\"'   
        }  
      }
   }
}


