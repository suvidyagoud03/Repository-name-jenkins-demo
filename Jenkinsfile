pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t jenkins-demo .'
            }
        }

        stage('Docker Image') {
            steps {
                sh 'docker images'
            }
        }
    }
}
stage('Deploy to Kubernetes') {
    steps {
        sh '''
            kubectl --kubeconfig=/var/lib/jenkins/.kube/config apply -f deployment.yaml
            kubectl --kubeconfig=/var/lib/jenkins/.kube/config apply -f service.yaml
        '''
    }
}
