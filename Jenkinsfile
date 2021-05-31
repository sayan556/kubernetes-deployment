pipeline {
  agent any
  stages {
    stage('Apply Kubernetes Files') {
      steps {
          withKubeConfig([credentialsId: 'kube-config']) {
          sh 'cat deployment.yaml'
          sh 'kubectl apply -f deployment.yaml'
         }
      }
    }
  }
}  
