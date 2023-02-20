pipeline {
	agent any
	
	stages {
		stage('Build') {
			steps {
				sh 'mvn -B -DskipTests clean install'
			}
		}
		stage('Testing') {
			steps {
				echo "test"
				sh 'mvn test'
			}
			post {
				always {
					junit 'target/surefire-reports/*.xml'
				}
			}
		}
		
	}
}
