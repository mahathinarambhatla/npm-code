pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
         sh 'cp .npmrc /home/jenkins'
         sh 'npm install'
        sh 'npm publish'
       }
       }
     }
} 
