pipeline {
    agent any

    environment {
        TF_IN_AUTOMATION = "true"
    }

    stages {
        stage('git checkout'){
            steps
            {
                git branch:'main',
                    url: 'https://github.com/bindumohan222015-create/terraformRepository'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }

    post {
        success {
            echo 'Terraform executed successfully!'
        }
        failure {
            echo 'Terraform execution failed!'
        }
    }
}

