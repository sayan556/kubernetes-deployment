pipeline {
  agent any
  stages {
    stage('Docker login'){
        steps{
            withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'password', usernameVariable: 'username')]) {
              sh 'docker login -u $username -p $password'
            }
        }
        
    }
    stage('Docker image build'){
        steps{
            sh 'docker build -t sayan-exam .'
            sh 'docker images'
        }
        
    }
    stage('Tag docker image'){
        steps{
            sh 'docker tag sayan-exam sayan556/kubernetes:newimage'
        }
        
    }
    stage('Push docker image'){
        steps{
            sh 'docker push sayan556/kubernetes:newimage'
        }
        
    }
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
