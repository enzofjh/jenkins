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
