pipeline {
	agent {  label 'linux agent' }
	stages {
		<!-- stage('---clean----'){
			tools {
				maven 'maven_3.9.5'
			}
			steps {
				sh 'mvn --version'
				sh "mvn clean"
			}
		} -->
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
				maven 'maven_3.9.5'
			}
			
			steps {
				sh 'mvn --version'
				sh "mvn package"
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
