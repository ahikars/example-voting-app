
pipeline {
  environment {
    registry = "ahikars"
    registryCredential = 'dockerhub'
  }
  agent {
    node {
      label 'ubuntu'
    }
  }
  stages {
    stage('login docker.io') {
      steps {
        sh 'docker login docker.io'
      }
    }
    stage('Build result') {
      steps {
        sh 'docker build -t ahikars/result ./result'
      }
    } 
    stage('Build vote') {
      steps {
        sh 'docker build -t ahikars/vote ./vote'
      }
    }
    stage('Build worker') {
      steps {
        sh 'docker build -t ahikars/worker ./worker'
      }
    }
    stage('Push result image') {
      
      steps {
        
          sh 'docker push ahikars/result'
        
      }
    }
    stage('Push vote image') {
            steps {
    
          sh 'docker push ahikars/vote'
        
      }
    }
    stage('Push worker image') {
     
      steps {
        
          sh 'docker push ahikars/worker'
        
      }
    }
  }
}
