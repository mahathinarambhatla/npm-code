pipeline 
{
  agent any
  tools {
    nodejs "node"
     }
 stages 
  {      
    stage('NPM Build') {
      when { expression { return fileExists('package.json')}}
        steps {
               sh 'npm install'
               }
    }
    stage('Maven Build') {
       when { expression { return fileExists('pom.xml')}}
         steps {
                sh 'mvn clean package'
           nexusArtifactUploader artifacts: [[artifactId: 'bytecode-viewer', classifier: '', file: 'target/bytecode-viewer-3.0.0.jar', type: 'jar']], credentialsId: 'nexus', groupId: 'the.bytecode.club', nexusUrl: '35.231.84.239:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-trial', version: '3.0.0'
            }
    }
     stage ('OWASP publish')
            {
              steps
              {
              dependencyCheckAnalyzer datadir: '', hintsFile: '', includeCsvReports: true, includeHtmlReports: true, includeJsonReports: true, includeVulnReports: true, isAutoupdateDisabled: true, outdir: '', scanpath: ' ${WORKSPACE}', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: ''
            dependencyCheckPublisher()
              }
            }
  }        
 }
