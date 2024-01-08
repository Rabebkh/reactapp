pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Push Docker Image') {
            steps {
                script {
                    // Utilisez votre ID de connexion DockerHub défini dans Jenkins
                    def dockerhubCred = credentials('dh_cred')

                    // Construire et pousser l'image Docker
                    docker.withRegistry('https://registry-1.docker.io', 'dockerhubCred') {
                        def customImage = docker.build("rabebkhaled/mini_projet:${env.BUILD_NUMBER}")
                        customImage.push()
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                // Ajoutez des étapes de déploiement si nécessaire
            }
        }
    }

    post {
        always {
            // Nettoyer les ressources ou effectuer d'autres actions après la construction
        }
    }
}
