pipeline {
	agent any
	
	tools {
		maven "My_Maven"
	}	


	stages {
		stage('Build') {
			steps {	sh 'mvn clean'
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
		stage('build docker file') {
                        steps { sh 'docker build -t addressbook:latest .'
                        }
                }
		stage('Tag Doker image') {
                        steps { sh 'docker tag addressbook:latest yashyash/adressbook:1.0'
                        }
                }
		stage('Tag Doker image') {
                        steps { sh 'docker tag addressbook:latest yashyash/adressbook:1.0'
                        }
                }
		stage('push Doker image') {
                        steps { 
				withCredentials([usernamePassword(credentialsId: 'DOCKER_CREDS', passwordVariable: 'DOCKER_HUB_PWD', usernameVariable: 'DOCKER_HUB_USER')]) {
				sh 'docker login -u $DOCKER_HUB_USER -p $DOCKER_HUB_PASS'
				sh 'docker push yashyash/adressbook:1.0'
				}
				
                        }
                }
	}
}

