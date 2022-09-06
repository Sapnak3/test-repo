pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo 'Building..'
            git branch: 'main', credentialsId: '173ebba3-ef36-4ebb-af69-b99362617a3b', url: 'https://github.com/Sapnak3/test-repo.git'   
            //build job: 'Functional Testing', parameters: [string(name: 'ENVIRONMENT_URL', value: 'http://qa-launch2020-ccss-ecms.connected.proterra.com.s3-website-us-east-1.amazonaws.com/#/login'), string(name: 'SELECT_BROWSER', value: 'Chrome')]
                   }
        }
            
        stage('Test') {
            steps {
                catchError {
                
                echo 'Testing..'
                
                bat '"C:\\Program Files\\Eggplant\\runscript.bat" "$WORKSPACE\\workspace\\FunctionalTesting\\CCSS_Edmonton.suite\\Scripts\\TestCases\\Demo\\TOUC_3301.script" -CommandLineOutput Yes -AlertOnError yes'
                
                }  
                
            }
        }
        
        stage ('cleanup') {
            steps{
           cleanWs()
            }
    }
        }
    }
