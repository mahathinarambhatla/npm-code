pipeline 
{
  agent any
  tools {nodejs "node"}
  stages 
  {      
     stage('Build') {
       steps{
        sh 'cp /root/.npmrc /var/lib/jenkins'
         sh 'echo $NPM_TOKEN'
        }
       }
       }
     } 
