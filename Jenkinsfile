pipeline {
	agent any
	stages{
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
		stage("Bring Grid Down"){
			steps{
				sh "docker-compose down"
			}
		}
	}
}