pipeline{
	environment 
	{
    		registry = "priyankadesai02/newapp"
   		registryCredential = 'priyankadesai02'
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
