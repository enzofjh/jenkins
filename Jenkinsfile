pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
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
		stage('Package') {
			steps {
				echo 'mvn package -DskipTests'
			}
		}
		stage('Build Docker Image'){
			steps {
				script {
					dockerImage = docker.build("enzojimenez/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		}
		stage('Push Docker Image'){
			steps {
				script {
					docker.withRegistry('','dockerhub'){
						dockerImage.push()
						dockerImage.push('latest')
					}
				}
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
