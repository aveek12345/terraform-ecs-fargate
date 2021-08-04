pipeline {
  environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }
   agent any
   tools {
  terraform 'terraform'
}
   stages {
    stage('Extract from Github') {
      steps {
        script {
          git branch: 'master', url: 'https://github.com/aveek12345/terraform-ecs-fargate.git'
          }
       }
    }
    
    stage('Terraform Init') {
      steps {
        script {
          bat 'terraform init'
          }
       }
    }
    
    stage('Terraform Plan') {
      steps {
        script {
          bat 'terraform plan'
          }
       }
    }
    
   
  }
  }

