pipeline {

	agent none
	stages {
		stage('Clone repository') {
		/* Let's make sure we have the repository cloned to our workspace */
			agent any
			steps {
				sh 'checkout scm'
			}
		}

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


