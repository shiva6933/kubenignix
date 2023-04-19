pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the Git repository
                git 'https://github.com/shiva6933/kubenignix'
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
