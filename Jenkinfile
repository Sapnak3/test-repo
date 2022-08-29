pipeline {
	agent any
		stages {
		stage('Build') {
			steps {
            catchError {
			   withCredentials([usernamePassword(credentialsId: 'SUT', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME')]) {
			   script{
			   bat  '''
			   "C:\\Program Files\\Eggplant\\runscript.bat"^
			   "D:\\26May\\26May\\CCSS_Edmonton.suite\\Scripts\\TestCases\Demo\\TOUC_3301.script" -param "http://qa-launch2020-ccss-ecms.connected.proterra.com.s3-website-us-east-1.amazonaws.com/#/login" -param "chrome"^
			   -host 3.81.234.4 -port 3389 -username "Administrator" -password "WCK=p(5yz0F.0eMm*rVwfIfwiMGmcO22" -type RDP -CommandLineOutput YES -GlobalResultsFolder "%WORKSPACE%\\%BUILD_NUMBER%\\ejmResults"
				'''
					}
				}
			}
		}
  }
    
