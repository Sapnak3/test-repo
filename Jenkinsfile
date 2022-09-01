pipeline {
    agent any
    options { skipDefaultCheckout() }
	stages{
	stage('git repo & clean') {
			steps{
                              // bat "rmdir /s /q test-repo.git" 
				bat "git clone https://github.com/Sapnak3/test-repo.git"
				bat "mvn clean -f Eggplant_Automation"
                             }
               }
		Stage('install') {
			           Steps{
			              bat "mvn install -f Eggplant_Automation"
				        }   
		}
		Stage('test') {
			           Steps{
			              bat "mvn test -f Eggplant_Automation"
				        }   
		}
		
		Stage('package') {
			           Steps{
			              bat "mvn package -f Eggplant_Automation"
				        }   
		}
		
					
		
    }
}
