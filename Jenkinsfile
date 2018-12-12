pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
        withCredentials([usernamePassword(credentialsId: 'nexus', passwordVariable: 'nexuspassword', usernameVariable: 'nexususer')]) {
        sh 'npm install'
        sh 'npm login --registry http://35.231.84.239:8081'
        sh 'npm publish --registry http://35.231.84.239:8081/repository/npm-trial/'
       }
       }
     }
  }
}  
