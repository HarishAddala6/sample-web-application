pipeline{

      agent {
                docker {
                image 'maven:3-alpine'
                args '-v $HOME/.m2:/root/.m2'
                }
            }
        
        stages{

              stage('Quality Gate Status Check'){
                  steps{
                      script{
		    	    sh "mvn sonar:sonar"
                 	}

               	 }  
              }	
	      stage('Clean Install'){
                  steps{
                      script{
		    	    sh "mvn clean install"
                 	}

               	 }  
              }	
		
            }	       	     	         
}
