pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID     = credentials('aws-access-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('aws-secret-access-key')
        AWS_REGION = 'ap-south-1'
    }

   stages{
        stage('clone repository'){
            steps{
                git 'https://github.com/akulamahendra/java-delpoyment.git'
            }
        }
        
        stage('terraform init'){
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform plan'){
            steps{
                sh 'terraform plan -out=tfplan'
            }
        }
        stage('terraform apply'){
            steps{
                sh 'terraform apply -auto-approve'
            }
        }
        stage('sleep 180'){
            steps{
                sh 'sleep 180'
            }
        }
   }
}
