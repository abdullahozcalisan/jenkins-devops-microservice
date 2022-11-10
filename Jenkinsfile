pipeline {
	agent any
	// agent { docker { image 'node:13.8'}}
	stages {
		stage('Test') {
			steps {
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"								
								
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
