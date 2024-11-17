node {
  stage('Clone repository') {
    git branch: 'main', credentialsId: 'github_access_token', url: 'https://github.com/cshyun7015/jenkins-django.git'
  }
  stage('Build image') {
    dockerImage = docker.build("cshyun/jenkins-django:v1.0")
  }
  stage('Push image') {
    withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
      dockerImage.push()
    }
  }
}
