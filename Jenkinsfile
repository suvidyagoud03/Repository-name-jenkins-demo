stage('Deploy to Kubernetes') {
    steps {
        sh '''
            kubectl --kubeconfig=/var/lib/jenkins/.kube/config apply -f deployment.yaml
            kubectl --kubeconfig=/var/lib/jenkins/.kube/config apply -f service.yaml
        '''
    }
}
