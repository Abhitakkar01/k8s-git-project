pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Abhitakkar01/k8s-git-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t k8s-flask-app .'
            }
        }

        stage('Load Image to Minikube') {
            steps {
                bat 'minikube image load k8s-flask-app'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f k8s/'
            }
        }
    }
}
