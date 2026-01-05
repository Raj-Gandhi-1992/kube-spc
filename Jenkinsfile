pipeline {
  agent {
    label 'spcjava'
  }
  stages {
    stage ('deploy_app_kubernetes') {
        steps {
            sh 'kubectl apply -f deploy/.'
        }
    }
    stage ('get_svc_details') {
        steps {
            sh 'kubectl get svc'
        }
    }
 }
}