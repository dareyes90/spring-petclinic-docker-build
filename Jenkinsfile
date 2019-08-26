pipeline {/*
  environment {
    registry = "deivy90/firstdockerrepo"
    registryCredential = 'dockerhub'
	dockerImage = ''
  }*/
  agent {
    label 'maven-docker'
  }
  stages {
	stage ('Build project'){
		steps {
		//container('maven') {
          sh 'mvn -version && ls -la'
          sh 'mvn clean install'
        //}
	  }
	}/*
	stage('Docker Build') {
      steps {
		container('docker'){
			script {
                                sh 'ls -la'
				dockerImage = docker build -t registry + ":$BUILD_NUMBER"
			}
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
    }*/
  }
}
