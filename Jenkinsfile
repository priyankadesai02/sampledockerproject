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
				sh 'mvn clean'
			}
		}
	}
}
