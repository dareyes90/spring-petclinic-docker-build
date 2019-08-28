pipeline {/*
  environment {
    registry = "deivy90/firstdockerrepo"
    registryCredential = 'dockerhub'
	dockerImage = ''
  }*/
  agent none
  stages {
	stage ('Build project'){
    agent {
      label 'maven-docker'
    }
		steps {
		//container('maven') {
          sh 'mvn -version && ls -la'
          sh 'mvn clean install'
        //}
	  }
	}
  stage ('Sonar Analysis'){
    agent {
      label 'general-docker'
    }
		steps {
          sh 'sonar-scanner'
	  }
	}

  /*
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
