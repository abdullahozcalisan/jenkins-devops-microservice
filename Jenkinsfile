pipeline {
	agent any
	environment {
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"								
								
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}

		stage('Integration test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}


		stage('Package') {
			steps {
				sh "mvn package -DskipTests"
			}
		}

		stage('Build Docker Image') {
			steps {
				// "docker build -t aozcalisan/currency-exchange:$env.BUILD_TAG"
				script {
					dockerImage = docker.build("aozcalisan/currency-exchange:${env.BUILD_TAG}")
				}

			
			}
		}

		stage('Push Docker Image') {
			steps {
				script {
					docker.withRegistry ('', 'dockerhub') {
						dockerImage.push();
						dockerImage.push('latest');
					}						
				} 
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
