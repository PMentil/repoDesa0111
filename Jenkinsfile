pipeline {
    agent any

    stages {
        stage('AWS VALIDATE') {
            steps {
                echo 'AWS STS'
                sh 'aws sts get-caller-identity'
        }
    }
        stage('AWS S3 listar') {
            steps {
                sh 'aws s3 ls'
            }
        } 
        stage('Git Clone') {
            steps {
                sh 'rm -rf desafio2710jekins/'
                sh 'git clone https://github.com/PMentil/desafio2710jekins.git'
                sh 'ls -lrt desafio2710jekins/'
            }
        } 
        stage('Upload to s3'){
            steps {
                sh 'aws s3 cp desafio2710jekins s3://jekins2710 --recursive'
            }
        }
    }
} 