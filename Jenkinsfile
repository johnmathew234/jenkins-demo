pipeline
{
 agent any
 stages{
 	stage('Build Application'){
   steps{
 	sh 'mvn clean install -DskipMunitTests' 	
 	}	
  }
  
  stage('Munit Tests'){
   steps{
    configFileProvider([configFile(fileId: 'da01fc76-5c2b-4f0d-948a-c101b4cc4340', variable: 'settings')]){
     sh 'mvn -f pom.xml -s $settings clean test'
    }
   }
  }

 	
 	stage('Deploy application to cloudHub'){
   steps{
    configFileProvider([configFile(fileId: 'da01fc76-5c2b-4f0d-948a-c101b4cc4340', variable: 'settings')]){
 	sh 'mvn -f pom.xml -s $settings -DmuleDeploy deploy -Dap.client_id=7ee076f5cfb04bb3b30fc37298232cbe -Dap.client_secret=a8ac5C5cB0574fd8971dF31156e3516c -Dapp.runtime.server=4.3.0 -Ddeployment.env=test -DskipMunitTests'
 	}
   }
  }
 	
 	
 	}
 }
