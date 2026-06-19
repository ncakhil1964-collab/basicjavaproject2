node(){

	
	stage('Code Checkout'){
		checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHubCreds', url: 'https://github.com/ncakhil1964-collab/basicjavaproject2']])
	}
	stage('Build Automation'){
		sh """
			ls -lart
			mvn clean install
			ls -lart target

		"""
	}
	
		stage('Code Deployment'){
		deploy adapters: [tomcat10(credentialsId: 'TomcatCreds', path: '', url: 'http://34.203.31.27:808/')], contextPath: 'Planview', onFailure: false, war: 'target/*.war'
	}
}
