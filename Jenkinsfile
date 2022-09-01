pipeline {
    agent none
    options { skipDefaultCheckout() }
	stages{
	stage('SCM Checkout') {
			agent { label 'main' }
			steps{
            bbs_checkout branches: [[name: '*/main]],
            credentialsId: 'github',
            id: 'sapnak3',
            mirrorName: '', projectName: 'Eggplant_Automation',
            repositoryName: 'test-repo', serverId: 'ec2-3-81-234-4.compute-1.amazonaws.com'
                }
         }
    }
}
