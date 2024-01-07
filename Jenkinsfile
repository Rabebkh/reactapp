pipeline {
    agent any
    triggers { 
        pollSCM('*/5 * * * *') 
    }    
    stages {
        stage('Checkout') {
            steps {
                echo "Récupération du code source"
                checkout scm 
            }
        }
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Build du projet" 
                sh 'yarn start'
            }
        }
    }
    
}
