pipeline {
  agent any
  stages {
    stage('Apply Kubernetes Files') {
      steps {
          withKubeConfig([credentialsId: 'kubeconfig']) {
          sh 'cat deployment.yaml'
          sh 'kubectl apply -f deployment.yaml'
         }
      }
    }
  }
}  
