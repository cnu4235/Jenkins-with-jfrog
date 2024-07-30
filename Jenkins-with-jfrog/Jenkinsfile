pipeline {
    agent any
    tools { 
        maven 'Maven 3.9.6' 
        // jdk '9.0.4'
    }

    stages {
		stage('Clean') {
		    steps {
			cleanWs()
			}
		}
		stage('Checkout') {
                       steps {
		   // checkout scm
		git branch: 'main', url: 'https://github.com/cnu4235/Jenkins-with-jfrog.git'
                        }
	        }
		stage ('Build') {
		    steps {
			echo "Maven is clening and gnerating artifactory"
			sh 'mvn clean install'
			}
		}
 }
}
