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
 
  }        
 }
