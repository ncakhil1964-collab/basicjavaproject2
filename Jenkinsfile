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
	
		stage('Code Deployment'){
		deploy adapters: [tomcat10(credentialsId: 'TomcatCreds', path: '', url: 'http://3.93.185.237:80/')], contextPath: 'Planview', onFailure: false, war: 'target/*.war'
	}
}
