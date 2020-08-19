pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                echo 'Running build'
                sh 'npm install --no-daemon'
                archieveArtifacts artifacts: 'dist/trainschedule.zip'
            }
        }
    }
}