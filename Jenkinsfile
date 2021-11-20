def getDockerTag() {
 def tag = sh script: 'git rev-parse HEAD', returnStdout: true 
 return tag
}
pipeline{

      agent any
      environment {
          Docker_tag = getDockerTag()
      }
        
        stages{

              stage('maven install'){
                  steps{
                      script{
			  
		    	    sh "mvn clean install"
		  
                 	}
               	 }  
              }	

              stage('build'){
		      steps {
			      script{
                sh 'docker build . -t HarishAddala6/sample-web-application:$Docker_tag'
         
                
			      }
		      }
              }
		
            }	       	     	         
}
