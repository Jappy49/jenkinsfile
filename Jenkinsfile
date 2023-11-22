pipeline {
	agent {  label 'linuxnode' }
	stages {
		stage('---clean----'){
			tools {
				maven 'maven_3.9.5'
			}
			steps {
				sh 'mvn --version'
				sh "mvn clean"
			}
		}
		stage('---test---') {
			tools {
				maven 'maven_3.9.4'
			}
			steps {
				sh 'mvn --version'
				sh "mvn test"
			}
		}
		stage('---package---'){
			tools {
				maven 'maven_3.9.0'
			}
			
			steps {
				sh 'mvn --version'
				sh "mvn package"
			}
		}
stage('---Archeive---')
	{
            archiveArtifacts artifacts: 'target/*.war'

	}
	stage('----deploy-----'){
	{
		
           //deploy adapters: [tomcat9(credentialsId: 'deploy', path: '', url: 'http://3.104.35.6:8080/')], contextpath: null, war: 'target/*.war'
	
	}
	}
	}
		
	post {
		success {
			echo 'job was built successfully'
		}
		failure {
			echo 'job was not build..it was failed'
		}
	}
} 
