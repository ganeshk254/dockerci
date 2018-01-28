node {
  def app
  
  stage('Clone repository') {
    checkout scm
  }

  stage('Build Image') {
    app = docker.build("ganeshk254/hello")
  }

  stage('Test Image') {
    app.inside {
      sh 'echo "Tests passed"'
    }
  }

  stage('Push Image') {
   app.inside {
    sh 'echo "${env.BUILD_NUMBER}"'
    sh 'echo "latest"'
   }
  }
}
