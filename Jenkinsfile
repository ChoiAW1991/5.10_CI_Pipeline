pipeline {
	agent any
	tools {
    	maven 'localMaven'
	}
	stages {
    	stage("Checkout") {   
        	steps {               	 
            	git url: 'https://github.com/ChoiAW1991/5.10_CI_Pipeline'          	 
           	 
        	}    
    	}

    	stage('Build') {
        	steps {
        	sh "mvn compile"  	 
        	}
    	}
   	 
    	stage("Unit test") {          	 
        	steps {  	 
            	sh "mvn test"          	 
       	        }
               
                post {
               		 always {
                	 	 junit '**/target/surefire-reports/TEST-*.xml'
                         }
                } 
    	}

    	stage("Package") {          	 
        	steps {  	 
            	sh "mvn package"          	 
       	    }
}
}
}
