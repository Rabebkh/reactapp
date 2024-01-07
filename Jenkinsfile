pipeline {
    agent any
    triggers { 
        pollSCM('*/5 * * * *') 
    }    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/Rabebkh/reactapp.git'
                
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
