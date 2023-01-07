pipeline {
    agent any
    stages {
        stage('Git checkout') {
           steps{
                git branch: 'main', credentialsId: 'Github', url: 'https://github.com/vchevychelov/terraform.git'
            }
        }
        stage('terraform Init') {
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform apply') {
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'main', url: "https://raw.githubusercontent.com/vchevychelov/boxfuse/master/deploy/playbook.yml"
            }
        }
        stage('Deploy') {
            steps {
                ansiblePlaybook playbook: 'playbook.yml', inventory: './inventory/hosts.ini', credentialsId: 'github_key'
            }
        }
    }
}