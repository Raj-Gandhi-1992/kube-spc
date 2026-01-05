pipeline {
  agent {
    label 'spcjava'
  }
  stages {
    stage ('kubernetes-config') {
        steps {
            sh '''
            cd .kube
            kubectl config current-context
            '''
        }
    }
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