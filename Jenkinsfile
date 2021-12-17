pipeline {
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				sh "docker pull alo453/selenium-docker"
			}
		}
		stage("Bring Grid Up"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up search-module1 book-flight-module1"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	}
}