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

		stage('Test image') {
		/* Ideally, we would run a test framework against our image.
		 * For this example, we're using a Volkswagen-type approach ;-) */
			agent any
			steps {}

		}

		stage('Push image') {
		/* Finally, we'll push the image with two tags:
		 * First, the incremental build number from Jenkins
		 * Second, the 'latest' tag.
		 * Pushing multiple tags is cheap, as all the layers are reused. */

			agent any
			steps {

				docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
					sh 'docker push rguyon/test:latest'
				}
			}
		}

	}
}


