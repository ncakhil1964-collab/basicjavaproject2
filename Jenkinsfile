node(){

	
	stage('Code Checkout'){
		checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/anujdevopslearn/MavenBuild']])
	}
	stage('Build Automation'){
		sh """
			mvn clean package spring-boot:repackage 

		"""
	}
	
	 stage('Deploy') {
        
deploy contextPath: null, war: 'java -jar myapp.jar'
    }
}
