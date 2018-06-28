// Powered by Infostretch 

timestamps {

node () {

	stage ('maven-project-package - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/menxumalo/maven-project.git']]]) 
	}
	stage ('maven-project-package - Build') {
 			// Maven build step
	withMaven(maven: 'localmaven') { 
 			if(isUnix()) {
 				sh "mvn clean package " 
			} else { 
 				bat "mvn clean package " 
			} 
 		}
		// Checkstyle report
		step([$class: 'CheckStylePublisher', canComputeNew: false, defaultEncoding: '', healthy: '90', pattern: '', unHealthy: '40'])
		archiveArtifacts allowEmptyArchive: false, artifacts: '**/*.war', caseSensitive: true, defaultExcludes: true, fingerprint: false, onlyIfSuccessful: false 
	}
	stage ('checkstyle - Build') {
 			// Maven build step
	withMaven(maven: 'localmaven') { 
 			if(isUnix()) {
 				sh "mvn checkstyle:checkstyle " 
			} else { 
 				bat "mvn checkstyle:checkstyle " 
			} 
 		} 
	}
	stage ('deploy - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.copyartifact.CopyArtifact". Please verify and convert manually if required. 
	}
	stage ('buildToProd - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.copyartifact.CopyArtifact". Please verify and convert manually if required. 
	}
}
}
