pipeline {
    agent any

    stages {
        stage('Deploy to kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'keumar', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://074fdc8b-0e7c-4ba7-8dac-fc7d35e0739b.us-east-2.linodelke.net:443']]) {
                sh "kubectl apply -f deployment-service.yml"
                
                
            }
        }
    }


        stage('verify deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'keumar', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://074fdc8b-0e7c-4ba7-8dac-fc7d35e0739b.us-east-2.linodelke.net:443']]) {
                    sh "kubectl get -n webapps"
            }
        }
    }    
  
}
}
