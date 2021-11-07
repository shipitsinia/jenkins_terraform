pipeline {
  agent {
    docker {
      image 'hashicorp/terraform:light'
      args '--entrypoint='
    }
  }
  stages {
    stage('Terraform Plan') { 
      steps {
        sh 'terraform plan -no-color -out=pbx.tfplan' 
      }
    }
    input 'Deploy stack?'

    stage ('Terraform Apply') {
      sh "terraform --version"
    }
  }
}
