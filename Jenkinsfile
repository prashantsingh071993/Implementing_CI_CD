pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                echo 'Running build'
                sh './gradlew build --no-daemon'
                archieveArtifacts artifacts: 'dist/trainschedule.zip'
            }
        }
    }
}