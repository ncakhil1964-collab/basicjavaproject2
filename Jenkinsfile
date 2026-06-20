node(){

	
	stage('Code Checkout'){
		checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/ncakhil1964-collab/basicjavaproject2']])
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
		deploy adapters: [tomcat9(credentialsId: 'TomcatCreds', path: '', url: 'http://13.222.190.56:8080/')], contextPath: null, onFailure: false, war: 'target/*.war'
	}
}
