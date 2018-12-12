pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
         sh 'npm adduser --registry=http://35.231.84.239:8081' --always-auth
         sh 'npm install'
        sh 'npm publish'
       }
       }
     }
} 
