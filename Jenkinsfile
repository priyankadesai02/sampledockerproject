pipeline{
	environment 
	{
    		registry = "priyankadesai02/NewApp"
   		registryCredential = 'Priyanka02'
  	}
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
		stage('Building image') 
		{
      			steps
			{
        			script
				{
          				docker.build registry + ":$BUILD_NUMBER"
        			}
      			}
    		}
	}
	
}
