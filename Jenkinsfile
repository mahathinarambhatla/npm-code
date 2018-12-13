pipeline 
{
  agent any
  tools {nodejs "node"}
  stages 
  {      
     stage('Build') {
       steps{
         sh 'cp .npmrc /var/lib/jenkins'
         sh 'npm login'
         sh 'npm install'
         sh 'npm publish'
        }
       }
       }
     } 
