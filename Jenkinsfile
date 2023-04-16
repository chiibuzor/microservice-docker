pipeline {
    agent any
    stages {
        stage('Clone Repo'){
            steps {
                git credentialsId: 'githubcreds', url: 'https://github.com/chiibuzor/microservice-docker.git'
            }
        }
        stage('Build JAR Artifacts '){
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Build Docker Image'){
            steps {
                sh 'docker-compose -f docker-compose-local.yml build'
            }
        }
        stage('Start Microservices'){
            steps {
                sh 'docker-compose -f docker-compose-local.yml up -d'
            }
        }
        
        }
    }  
