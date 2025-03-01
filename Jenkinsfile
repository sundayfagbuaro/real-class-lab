pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                script {
                    git branch: 'rds_mysql', credentialsId: 'git_cred', url: 'https://github.com/sundayfagbuaro/real-class-lab.git'
                
                }
            }
        }

        stage('Terraform init') {
            steps {
                sh "terraform init"
            }
        }

        stage('Terraform Action') {
            steps {
                withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', 
                credentialsId: 'Jenkins-aws-cred', 
                secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                    
                    sh "terraform ${Actions} --auto-approve"
            }
            }
        }
    }
}

