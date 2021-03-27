pipeline {

  agent { label 'kubepod' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/santoshsm/kubedeploystatecode.git', branch:'master'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deploy-statecode.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
