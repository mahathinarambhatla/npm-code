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
            dependencyCheckAnalyzer datadir: '', hintsFile: '', includeCsvReports: false, includeHtmlReports: false, includeJsonReports: false, includeVulnReports: false, isAutoupdateDisabled: false, outdir: '', scanpath: ' ${WORKSPACE}', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: ''
            dependencyCheckPublisher()
            }
    }
  }
 }
