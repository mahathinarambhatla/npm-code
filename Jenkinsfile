pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
         sh 'whoami'
         sh 'npm install'
        sh 'npm publish'
       }
       }
     }
} 
