pipeline {
    agent any

    stages {

        stage('terraform started') {
            steps {
                sh 'echo "Started...!" '
            }
        }
        stage('git clone') {
            steps {
                sh 'sudo rm -r *;sudo git clone https://github.com/kdevesh/terraform.git'
            }
        }
        stage('tfsvars create'){
            steps {
                sh 'sudo cp /home/devopsuser/values.tfvars ./terraform/'
            }
        }
        stage('terraform init') {
            steps {
                sh 'sudo /usr/local/bin/terraform init ./terraform'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'ls ./terraform; sudo /usr/local/bin/terraform apply -var-file="./terraform/values.tfvars" -auto-approve ./terraform'
            }
        }
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }

        
    }
}