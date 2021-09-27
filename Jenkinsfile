properties([ parameters([
  string( name: 'AWS_ACCESS_KEY_ID', defaultValue: ''),
  string( name: 'AWS_SECRET_ACCESS_KEY', defaultValue: ''),
]), pipelineTriggers([]) ])

// Environment Variables.
env.access_key = AWS_ACCESS_KEY_ID
env.secret_key = AWS_SECRET_ACCESS_KEY

pipeline {
    agent any
    stages {
         stage ('Terraform Init'){
            steps {
            sh "terraform init"
          }
       }
         stage ('Terraform Plan'){
            steps {
            sh "terraform plan" 
         }
      }
         stage ('Terraform Apply - Create Instances and Configurig Clustering'){
            steps {
            sh "terraform apply -auto-approve"
        }
      }
    }
  }