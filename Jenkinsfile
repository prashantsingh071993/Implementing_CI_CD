pipeline {
    agent any
    stages {
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
                    docker.withRegistry('https://registry.hub.docker.com', 'Docker_hub_id')
                    app.push("${env.BUILD_NUMBER}")
                    app.push("latest")
                }
            }
        }    
        }
    }
