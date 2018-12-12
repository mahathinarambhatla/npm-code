pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
        sh 'cp .npmrc /var/lib/jenkins'
        sh 'npm whoami'
        sh 'npm install'
        sh 'npm publish'
       }
       }
     }
} 
