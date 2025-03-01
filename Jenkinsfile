pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                script {
                    git branch: 'main', credentialsId: 'git_cred', url: 'https://github.com/sundayfagbuaro/real-class-lab.git'
                
                }
            }
        }

        stage('Terraform init') {
            steps {
                sh "terraform init"
            }
        }
    }
}

