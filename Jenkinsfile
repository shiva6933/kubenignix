pipeline {
    agent any
    
    stages {
        stage('Copy file to Minikube') {
            steps {
                sh 'eval $(minikube docker-env) && docker cp nginx.yaml $(minikube docker-env | grep DOCKER_HOST | cut -d/ -f3-):/nginx.yaml'
            }
        }
        stage('Apply file to Minikube') {
            steps {
                sh 'kubectl apply -f nginx.yaml'
            }
        }
    }
}
