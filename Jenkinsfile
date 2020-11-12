pipeline {
	agent any
	stages {
		stage("Build") {
			steps {
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
			echo "always"
		}
		success {
			echo "this is success"
		}
		failure {
			echo "FAILED"
		}
	}
}
