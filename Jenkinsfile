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
                withKubeConfig([credentialsId: 'kubeconfig', serverUrl: 'https://192.168.49.2:8443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
']) {
                sh 'kubectl apply -f nginx.yml -n default'
                }
            }
        }
    }
}
