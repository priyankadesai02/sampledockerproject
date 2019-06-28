pipeline{
	agent any
		tools
		{
			jdk "javahome"
			maven "mavenhome"
		}
	stages
	{
		stage('Build')
		{
			steps
			{
				sh 'mvn clean install'
			}
		}
		stage('Push to Docker Registery')
		{
			withCredentials([usernamePassword(credentialsId: 'dockerHubAccount', usernameVariable: 'priyankadesai02', passwordVariable: 'Priyanka02')])
			pushToImage(tomcatApp, Projectpipe, priyankadesai02, Priynka02)
		}
	}
	
}
