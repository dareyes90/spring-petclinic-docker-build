
pipeline {
  environment {
    registry = "deivy90/firstdockerrepo"
    registryCredential = 'dockerhub'
	dockerImage = ''
  }
  agent {
    label 'maven-docker'
  }
  stages {
    stage('Docker Build') {
      steps {
        container('docker'){
          dockerImage = docker build -t registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Docker Push') {
      steps {
		script {
			docker.withRegistry( ‘’, registryCredential ) {
			dockerImage.push()
			}
		}
      }
    }
  }
}
