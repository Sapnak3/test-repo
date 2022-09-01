pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo 'Building..'
            git branch: 'main', credentialsId: 'd5167762-58a0-471e-a70e-4898448e767f', url: 'https://github.com/Sapnak3/test-repo.git'   
            build job: 'Functional Testing', parameters: [string(name: 'ENVIRONMENT_URL', 
            value: 'http://qa-launch2020-ccss-ecms.connected.proterra.com.s3-website-us-east-1.amazonaws.com/#/login'), 
            string(name: 'SELECT_BROWSER', value: 'Chrome')]
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], 
                          userRemoteConfigs: [[credentialsId: 'd5167762-58a0-471e-a70e-4898448e767f', 
                                               url: 'https://github.com/Sapnak3/test-repo.git']]])
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
