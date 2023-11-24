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
			post{
				success{
					echo 'job was built successfully'
			echo "Archeiving the artifacts"
		archiveArtifacts artifacts: '**/target/*.war'
				}
				
			}
			
		}
	
	
	
	stage('---tomcat---'){
	steps {
deploy adapters: [tomcat9(credentialsId: '4da08f1c-7ef8-4d84-8929-2f51fb1705ca', path: '', url: 'http://13.239.118.44:8080/')], contextPath: null, war: '*.war'
	}
	}
	}
	
}
