pipeline {
    agent {
        docker { image 'node:14-alpine' }
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
