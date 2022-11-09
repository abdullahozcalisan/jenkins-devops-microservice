pipeline {
	// agent any
	agent { docker { image 'maven:3.6.3'}}
	stages {
		stage('Test') {
			steps {
				echo 'mvn --version'
			}
		}
		stage('Build') {
			steps {
				echo "This"
				echo "is"
				echo "build stage"
			}
		}		
		stage('Deploy') {
			steps {
				echo "This"
				echo "is"
				echo "deploy stage"
			}
		}			
	}
	post {
		always {
			echo 'ı run always'
		}
		success {
			echo  'ı run only job is success'
		}
		failure {
			echo 'ı run only job is failure'
		}
	}
}
