pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
    		steps{
    			bat "docker pull vitalis07/selenium-docker"
    			}
    	}
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
	}
	post{
	    always{
	        archiveArtifacts artifacts: 'output/**'
	        bat "docker-compose down"
	    }
	}
}