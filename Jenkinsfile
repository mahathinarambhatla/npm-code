pipeline 
{
  agent any
    
  tools {nodejs "node"}
 
  stages 
  {      
     stage('Build') {
       steps{
        nodejs(nodeJSInstallationName: 'node', configId: '684ce885-0945-49c8-b4ca-445dd7bd9b7b') {
        sh 'cp .npmrc /var/lib/jenkins'
        sh 'npm login'
        sh 'npm install'
        sh 'npm publish'
        }
       }
       }
     }
} 
