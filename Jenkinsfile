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
		stage ('Build') {
		    steps {
			echo "Maven is clening and gnerating artifactory"
			sh 'mvn clean install'
			}
		}
	}
}
