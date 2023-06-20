pipeline {
    agent any
    stages {
        stage('clone the code 0f salore') {
            steps {
                git url: 'https://github.com/maramvenkatareddy/deploy.git', 
                    branch: 'main'
            }
        }
        stage('build the image') {
            steps {
                sh 'kubectl rollout restart deployment nginx-deployment'
                sh 'kubectl config current-context'
                sh 'kubectl apply -f service.yaml'
                sh 'kubectl apply -f configmap.yaml'
                sh 'kubectl apply -f hpa.yaml'
                sh 'kubectl get po -A'
            }
        }
    }
    
}
