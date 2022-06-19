pipeline {
	agent any
	stages {
		stage('Checkout') {
			steps {
					git 'https://github.com/chandanbms/repo'
				}
		}
		
	
		stage('Compile') {
		    steps {
		        dir('') {
		             sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn compile'
		        }
		    }
		}
		
		stage('Review') {
		    steps {
		        dir('') {
		             sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn -P metrics pmd:pmd'
		        }
		    }
		}
		
		stage('Test') {
		    steps {
		        dir('') {
		             sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn test'
		        }
		    }
		}
		
		stage('Build') {
		    steps {
						dir('') {
						sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn -B -V -U -e clean package'
						}
					}
		}
		
		
		
		}
		
}
