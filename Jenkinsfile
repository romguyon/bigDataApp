pipeline {

	agent none
	stages {

		stage('Build image') {
		/* This builds the actual image; synonymous to
		 * docker build on the command line */
			agent any
			steps {
				sh 'docker build -t rguyon/test:latest .'
			}
		
	    	}



	}
}


