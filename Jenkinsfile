node(){
      agent any
    stages {
        stage('Code Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/master']],
                          userRemoteConfigs: [[url: 'https://github.com/ncakhil1964-collab/basicjavaproject2.git',
                                               credentialsId: 'GitHubCreds']]])
            }
        }
        stage('Build Automation') {
            steps {
                sh './mvnw clean install'
            }
        
	
		stage('Code Deployment'){
		deploy adapters: [tomcat10(credentialsId: 'TomcatCreds', path: '', url: 'http://3.93.185.237:80/')], contextPath: 'Planview', onFailure: false, war: 'target/*.war'
	}
}
