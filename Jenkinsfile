pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH+EXTRA = '$dockerHome/bin:$mavenHome:bin'
	}

	stages {
		stage('Build"') {
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo 'Build'
			}
		}
		stage('Test') {
			steps {
				echo 'Test'
			}
		}
		stage('Integration') {
			steps {
				echo 'Integration'
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
