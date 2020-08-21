node {

  checkout scm
  def dockerImage

  stage('Build image') {
    dockerImage = docker.build("prashantsingh07/train-schedule:latest")
  }

  stage('Push image') {
    docker.withRegistry('https://registry-1.docker.io/v2/', 'docker_hub_login') {
      dockerImage.push()
    }
  }

}