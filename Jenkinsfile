pipeline 
{
  agent any
  tools {nodejs "node"}
  stages 
  {      
     stage('Build') {
       steps{
         sh 'npm login'
         sh 'npm install'
         sh 'npm publish'
        }
       }
       }
     } 
