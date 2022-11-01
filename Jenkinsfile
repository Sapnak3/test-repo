pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo 'Building..'
            git branch: 'main', credentialsId: 'SapnaKumari314', url: 'https://github.com/SapnaKumari314/test-repo.git'   
                               }
        }
            
        stage('Test') {
            steps {
                catchError {
                
                echo 'Testing..'
                
                bat '"C:\\Program Files\\Eggplant\\runscript.bat" "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\FunctionalTesting\\test-repo\\patch-4\\Eggplant_Automation\\CCSS_Edmonton.suite\\Scripts\\TestCases\\Demo\\TOUC_3301.script" -CommandLineOutput Yes -AlertOnError yes -LicenserHost ec2-54-210-217-115.compute-1.amazonaws.com'
                    
                }  
                
            }
        }
        
       
        }
    }
