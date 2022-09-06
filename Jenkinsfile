pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo 'Building..'
            git branch: 'main', credentialsId: 'c851c236-8982-459b-830b-88e7be6e28bd', url: 'https://github.com/Sapnak3/test-repo.git'   
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
