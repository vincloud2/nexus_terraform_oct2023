pipeline {
    agent { label "slave1" }

    stages {
        stage('Git GET nexus IAC ') {
            steps {
                echo 'Git GET nexus IAC'
                git branch: 'main', credentialsId: 'git_hub_vincloud2', url: 'https://github.com/vincloud2/nexus_terraform_oct2023.git'
            }
        }        
        stage('Terraform initialization stage') {
            steps {
                echo 'Terraform initialization stage'
                sh 'terraform init'
            }
        }
        stage('Terraform Plan stage') {
            steps {
                echo 'Terraform Plan stage'
                sh 'terraform plan'
            }
        }
        stage('Terraform validate') {
            steps {
                echo 'Terraform validate stage'
                sh 'terraform validate'
            }
        }        
        stage('Terraform apply') {
            steps {
                echo 'Terraform apply'
                sh 'terraform apply -auto-approve'
            }
        }        
    }
}
