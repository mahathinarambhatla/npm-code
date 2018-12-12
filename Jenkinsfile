pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('TEST npm whoami') {
        withCredentials([usernamePassword(credentialsId: 'nexus', passwordVariable: 'nexuspassword', usernameVariable: 'nexususer')]) {
        sh 'npm install'
        sh 'npm publish --registry http://35.231.84.239:8081/repository/npm-trial/'
       }
       }
     }
}
