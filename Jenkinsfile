pipeline
{
 agent any
 stages{
 	stage('Build Application'){
   steps{
 	bat 'mvn clean install' 	
 	}	
  }
 	
 	stage('Deploy application to cloudHub'){
   steps{
 	bat 'mvn -DmuleDeploy deploy -Dap.client_id=7ee076f5cfb04bb3b30fc37298232cbe -Dap.client_secret=a8ac5C5cB0574fd8971dF31156e3516c -Dapp.runtime.server=4.3.0 -Ddeployment.env=dev'
 	}
  }
 	
 	
 	}
 }
