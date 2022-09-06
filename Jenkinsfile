pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo 'Building..'
            git branch: 'main', credentialsId: '3de8d39f-d506-4645-aabf-2a650ec732a4', url: 'https://github.com/Sapnak3/test-repo.git'   
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
