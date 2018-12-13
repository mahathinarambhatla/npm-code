pipeline 
{
  agent any
  tools {nodejs "node"}
  stages 
  {      
     stage('Build') {
       steps{
         sh 'npm-cli-login -u admin -p admin123 -e admin@example.org -r http://35.231.84.239:8081/repository/npm-trial'
          sh 'npm install'
         sh 'npm publish'
        }
       }
       }
     } 
