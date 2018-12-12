pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Install dependencies') 
     {
      steps 
       {
         sh 'npm install'
         sh 'npm publish --registry http://35.231.84.239:8081/repository/npm-trial/'
        }
       }
     }
}
