pipeline {
    agent any
    stages {
        stage('Build image') {
            steps {
                // Build the Docker image
                sh 'docker build -t my-nginx-image .'
            }
        }
        stage('Push image') {
            steps {
                // Push the Docker image to a container registry
                sh 'docker push my-nginx-image'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                // Apply the Kubernetes configuration
                sh 'kubectl apply -f nginx.yml -n default'
            }
        }
    }
}
