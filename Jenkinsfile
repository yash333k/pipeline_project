pipeline {
	agent any
	
	tools {
		maven: My_Maven
	}	


	stages {
		stage('Build') {
			steps {
				sh 'mvn clean'

			}
		}
		stage('Test') {
			steps { sh 'mvn test'
			}
		}
		stage('Compile') {
			steps { sh 'mvn compile'
			}
		}
		stage('pakage') {
			steps { sh 'mvn package'
			}
		}
	}
}
