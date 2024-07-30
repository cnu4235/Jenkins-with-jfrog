pipeline {
    agent any
    tools { 
        maven 'Maven 3.9.6' 
        // jdk '9.0.4'
    }
    environment {
     CI = true
     ARTIFACTORY_ACCESS_TOKEN = credentials('artifactory-access-token')
     JFROG_PASSWORD  = credentials('jfrog-password')
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
		stage('Upload Binaries to Jfrog Artifactory') {
        		steps {
        	sh 'jf rt upload --url http://3.14.126.223:8082/artifactory --access-token ${ARTIFACTORY_ACCESS_TOKEN} target/my-app-1.0-SNAPSHOT.jar java-web-app/'
          }
        }		
 }
}
