pipeline {
    agent {
        docker {
            image 'hashicorp/terraform:light'
            args '-i --entrypoint='
        }
    }
    environment {
        aws_access_key = credentials('aws_access_key')
        aws_secret_key = credentials('aws_secret_key')
    }
    stages {
        stage('Terraform') {
            steps {
                sh 'terraform plan -no-color -out=pbx.tfplan'
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform --version'
            }   
        } 
    } 
}
