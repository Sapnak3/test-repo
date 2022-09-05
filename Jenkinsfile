pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo 'Building..'
            git branch: 'main', credentialsId: 'd5167762-58a0-471e-a70e-4898448e767f', url: 'https://github.com/Sapnak3/test-repo.git'   
            //build job: 'Functional Testing', parameters: [string(name: 'ENVIRONMENT_URL', value: 'http://qa-launch2020-ccss-ecms.connected.proterra.com.s3-website-us-east-1.amazonaws.com/#/login'), string(name: 'SELECT_BROWSER', value: 'Chrome')]
                   }
        }
            
        stage('Test') {
            steps {
                echo 'Testing..'
                bat '"C:\\Program Files\\Eggplant\\runscript.bat" "D:\\26May\\26May\\CCSS_Edmonton.suite\\Scripts\\TestCases\\Demo\\TOUC_3301.script" -CommandLineOutput Yes -AlertOnError yes'
                
                
            }
        }
        
        stage ('cleanup') {
           cleanWS()
            
    }
        }
    }
