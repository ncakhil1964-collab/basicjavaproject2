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
		sh 'pkill -f "java -jar" || true'
                sh 'nohup java -jar target/*.jar > app.log 2>&1 &'
}
}

