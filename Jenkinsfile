pipeline {
    agent any
    environment {

    }
    stages {
        stage('Deploy App') {
            steps {
                sh "kubectl apply -f flask-app.yaml"
            }
        }
        stage('Deploy NGINX') {
            steps {
               sh "kubectl apply -f nginx-config.yaml" 
            }
        }
    }
}