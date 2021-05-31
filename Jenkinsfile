pipeline {
  agent any
  stages {
    stage('Apply Kubernetes Files') {
      steps {
          withKubeConfig([credentialsId: 'kube']) {
          sh 'cat deployment.yaml'
          sh 'kubectl apply -f deployment.yaml'
         }
      }
    }
  }
}  
