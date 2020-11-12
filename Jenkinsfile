pipeline {
	//agent any
	agent {
		docker {
			image 'maven:3.6.3'
		}
	}
	stages {
		stage("Build") {
			steps {
				sh "mvn --version"
				echo "Build"
			}
		}
		stage("Test") {
			steps {
				echo "Test"
			}
		}
		stage("Integration") {
			steps {
				echo "Integration"
			}
		}
	}
	post {
		always {
			echo "ALWAYS"
		}
		success {
			echo "This is SUCCESS"
		}
		failure {
			echo "This is FAILED"
		}
	}
}
