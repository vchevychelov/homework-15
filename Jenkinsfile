pipeline {
    agent any
    tools {
       terraform 'terraform'
    }
    stages {
        stage('terraform destroy') {
            steps{
                sh 'terraform destroy'
            }
        }
    }
}