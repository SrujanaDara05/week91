pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 srujanadara/registration:v1'
                bat 'docker push srujanadara/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/Users/ASUS/OneDrive/Desktop/Devops/Week-2/deployment.yaml'
                bat 'kubectl apply -f C:/Users/ASUS/OneDrive/Desktop/Devops/Week-2/service.yaml'
            }
        }
        stage('Automated UI Test') {
steps {
bat 'C:\Users\ASUS\OneDrive\Desktop\Devops\Week-2\test_registration.py';
}
}
    }
}
