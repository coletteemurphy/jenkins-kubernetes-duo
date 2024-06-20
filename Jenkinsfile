pipeline {
    agent any
    environment {
        VERSION = "V1"
    }
    stages {
        stage('Delete old'){
            steps {
                sh 'kubectl delete -f . ||  true'
            }    
        }
        stage('Deploy App') {
            steps {
                sh "kubectl apply -f flask-app.yaml"
            }
        }
        stage('Deploy NGINX') {
            steps {
               sh "kubectl apply -f nginx-config.yaml" 
               sh "kubectl apply -f app-config.yaml"
               sh "sleep 10"
               sh "kubectl get svc"

            }
        }
    }
}