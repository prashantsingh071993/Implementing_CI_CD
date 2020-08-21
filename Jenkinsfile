pipeline {
    agent any
    stages {
        stage ('Docker Login'){
            steps {
                sh 'docker login -u $DOCKER_USER -p $DOCKER_PASSWORD'

            }
            
        }
        stage ('Build Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    app = docker.build("prashantsingh07/train-schedule")
                   
                }
            }
        
           
            }
        stage ('Push Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com/', 'docker_hub_login')
                    app.push("${env.BUILD_NUMBER}")
                    app.push("latest")
                }
            }
        }    
        }
    }
