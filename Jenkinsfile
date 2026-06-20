node(){

	
	stage('Code Checkout'){
		checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/anujdevopslearn/MavenBuild']])
	}
	stage('Build Automation'){
		sh """
			ls -lart
			mvn -version
			mvn clean install
			ls -lart target

		"""
	}
	
	 stage('Deploy') {
        
deploy contextPath: null, war: 'java -jar myapp.jar'
    }
}
