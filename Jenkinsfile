pipeline 
{
  agent any
  tools {
    nodejs "node"
    maven 'apache-maven-3.3.9' }
 stages 
  {      
    stage('NPM Build') {
      when { expression { return fileExists('package.json')}}
        steps {
            sh 'cp .npmrc /var/lib/jenkins'
            sh 'npm install'
            sh 'npm publish'
            }
    }
    stage('Maven Build') {
       when { expression { return fileExists('pom.xml')}}
         steps {
                sh 'mvn clean package'
           nexusArtifactUploader artifacts: [[artifactId: 'bytecode-viewer', classifier: '', file: 'target/bytecode-viewer-3.0.0.jar', type: 'jar']], credentialsId: 'nexus', groupId: 'the.bytecode.club', nexusUrl: '35.231.84.239:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-trial', version: '3.0.0'
            }
    }
   stage('Docker Image Build and Push To Nexus')
        {
            when 
            {
                expression { return fileExists('Dockerfile')}
		    }
           steps
            {
	         sh 'docker build -f "Dockerfile" -t trial:1.0  .'  
                 withDockerRegistry(credentialsId: 'b9ba9580-ebea-417d-b0d3-17857027692b', url: 'http://35.231.84.239:8082') 
                     {
			          sh '''
			           whoami
			            docker tag "trial1.0" "docker-trial/trial" 
			             docker push  "docker-trial/trial" 
			                  '''
                     }                  
		    }
        }
  }        
 }
