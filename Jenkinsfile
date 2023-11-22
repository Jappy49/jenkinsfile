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
	
	stage('----deploy-----')
	{
		
	steps {
		
		sh 'scp -rp /home/ec2-user/linuxnode/workspace/techprimers.war -i tomcatdeploy.pem ec2-user@3.104.35.6:/home/ec2-user/apache-tomcat-9.0.83/webapps'
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
