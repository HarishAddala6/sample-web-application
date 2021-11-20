def getDockerTag() {
 def tag = sh script: 'git rev-parse HEAD', returnStdout: true 
 return tag
}
pipeline{

      agent {
                docker {
                image 'maven'
                args '-v $HOME/.m2:/root/.m2'
                }
             }
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
