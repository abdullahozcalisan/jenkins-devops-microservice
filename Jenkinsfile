pipeline {
	agent any
	stages {
		stage('Test') {
			steps {
				echo "This"
				echo "is"
				echo "test stage"
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
