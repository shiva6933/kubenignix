pipeline {
    agent any
    stages {
        
        stage('Checkout Source') {
      steps {
        git url:'https://github.com/shiva6933/kubenignix.git', branch:'master'
      }
    }
        stage('Deploy to Kubernetes') {
            steps {
                // Apply the Kubernetes configuration
                withKubeConfig([credentialsId: 'kubeconfig', serverUrl: 'https://192.168.49.2:8443']){
                sh 'kubectl apply -f nginx.yml -n default'
                }
            }
        }
    }
}
