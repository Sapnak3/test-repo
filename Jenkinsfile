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
		//stage('install') {
			           //steps{
			              //bat "mvn install -f Eggplant_Automation"
				       // }   
		//}
		stage('test') {
			           steps{
			              bat "mvn test -f Eggplant_Automation"
				        }   
		}
		
		//stage('package') {
			           //steps{
			            //  bat "mvn package -f Eggplant_Automation"
				        //}   
		//}
		
					
		
    }
}
