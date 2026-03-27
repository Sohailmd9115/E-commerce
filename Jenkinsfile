pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/Sohailmd9115/E-commerce.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("ecommerce-app")
                }
            }
        }

        stage('Trivy Scan') {
            steps {
                sh 'trivy image ecommerce-app'
            }
        }

    }
}