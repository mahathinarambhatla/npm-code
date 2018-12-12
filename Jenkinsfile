pipeline 
{
  agent any
    
  tools {nodejs "node"}
    
  stages 
  {      
     stage('Build') {
       steps{
         sh '''  TOKEN=$(curl -s \
         -H "Accept: application/json" \
         -H "Content-Type:application/json" \
        -X PUT --data '{"name": "admin", "password": "admin123"}' \
        http://35.231.84.239:8081/-/user/org.couchdb.user:admin 2>&1 | grep -Po \
         '(?<="token": ")[^"]*')  '''
         sh 'npm set registry http://35.231.84.239:8081/:_authToken $TOKEN'
        sh 'npm install'
        sh 'npm publish'
       }
       }
     }
} 
