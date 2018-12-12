pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
         sh ' ~/.npmrc'
         sh 'npm install'
        sh 'npm publish'
       }
       }
     }
} 
