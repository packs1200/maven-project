// Powered by Infostretch 

timestamps {

node () {

	stage ('package - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/packs1200/maven-project.git']]]) 
	}
	stage ('package - Build') {
 			// Maven build step
	withMaven(maven: 'maven 3.6.3') { 
 			if(isUnix()) {
 				sh "mvn clean package " 
			} else { 
 				bat "mvn clean package " 
			} 
 		}
		archiveArtifacts allowEmptyArchive: false, artifacts: '**/target/*.war', caseSensitive: true, defaultExcludes: true, fingerprint: false, onlyIfSuccessful: false 
	}
	stage ('deploy-to-staging - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.copyartifact.CopyArtifact". Please verify and convert manually if required. 
	}
	stage ('deploy-to-staging-production - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.copyartifact.CopyArtifact". Please verify and convert manually if required. 
	}
	stage ('test - Build') {
 			// Maven build step
	withMaven(maven: 'maven 3.6.3') { 
 			if(isUnix()) {
 				sh "mvn checkstyle:checkstyle " 
			} else { 
 				bat "mvn checkstyle:checkstyle " 
			} 
 		} 
	}
}
}
