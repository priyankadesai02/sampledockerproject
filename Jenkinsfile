pipeline{
	environment 
	{
    		registry = "priyankadesai02/newapp"
   		registryCredential = 'docker-hub-credentials'
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
		stage('Deploy Image') 
		{
 			steps
			{
   				 script
				 {
      					docker.withRegistry( '', registryCredential )
					 {
						dockerImage.push()
					 }
				 }
			}
		}
	}
}
