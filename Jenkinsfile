pipeline {
    agent any
    stages {
        stage('Git checkout') {
           steps{
                git branch: 'main', credentialsId: 'Github', url: 'https://github.com/vchevychelov/terraform.git'
            }
        }
        stage('terraform destroy') {
            steps{
                sh 'terraform destroy --auto-approve'
            }
        }
    }
}