pipeline {
    agent any 
    stages {
        stage('Checkout from Git') { 
            steps {
                git branch: 'main' , url: 'https://github.com/Karthik351/Terraform-Jenkins-EC2.git'
            }
        }
        stage('Terraform version') { 
            steps {
                script {
                    sh 'terraform --version'
                }
            }
        }
        stage('Terraform init') { 
            steps {
                script {
                    sh 'terraform init'
                }
            }
        }
        stage('Terraform validate') { 
            steps {
                script {
                    sh 'terraform validate'
                }
            }
        }
        stage('Terraform Plan') { 
            steps {
                script {
                    sh 'terraform plan'
                }
            }
        }
        stage('Terraform Apply') { 
            steps {
                script {
                    sh 'terraform apply --auto-approve'
                }
            }
        }
        stage('Approve to Destroy') { 
            steps {
               input message: 'Approve to Destroy', ok: 'Destroy'
            }
        }
        stage('Terraform Destroy') { 
            steps {
                script {
                    sh 'terraform destroy --auto-approve'
                }
            }
        }
    }
}
