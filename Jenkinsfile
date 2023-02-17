pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
				}
		}
		stage("Run Tests"){
        			steps{
        				bat "docker-compose up search-module"
        				}
        		}
		stage("Stop Grid"){
			steps{
				bat "docker-compose down"
				}
		}
	}	
}