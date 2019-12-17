pipeline {
  agent any
  environment {
    registryCredential = 'dockerhub'
  }
  stages {
   stage('build') {
	steps {
	  sh 'docker build -t mohsinejaz/project-fib-server .'
           }
      }
    stage('Publish') {
        steps{
            script {
                docker.withRegistry( '', registryCredential ) {
		 sh 'docker push mohsinejaz/project-fib-server:latest'
               } 
           }
        }       
    }
  }
}
