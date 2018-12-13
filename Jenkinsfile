pipeline 
{
  agent any
  tools {nodejs "node"}
  stages 
  {      
     stage('Build') {
       steps{
        sh 'npm config set registry http://35.231.84.239:8081/repository/npm-trial'
        sh ''' 
        npm login --registry http://35.231.84.239:8081/repository/npm-trial < auth.txt 
        '''
        sh 'npm install'
        sh 'npm publish'
        }
       }
       }
     } 
