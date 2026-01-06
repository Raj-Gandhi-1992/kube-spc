pipeline {
  agent {
    label 'spcjava'
  }
  stages {
    stage ('aws-config') {
        steps {
             withCredentials([['AmazonWebServicesCredentialsBinding',credentialsId:'aws-eks'], file(credentialsId:'kubeconfig-eks', variable: 'KUBECONFIG') ])

            sh '''
            kubectl apply -f deploy/.
            kubectl get svc
            '''
        }
    }

 }
}