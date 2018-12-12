pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
        sh 'npm whoami'
        sh 'npm install'
        sh 'npm publish'
       }
       }
     }
} 
