pipeline {
  agent any
  stages{
    stage("checkout"){
      steps{
        checkout scm
      }
    }

    stage('Test Docker') {
      steps {
        sh 'docker --version'
      }
    }

    stage("test"){
      agent {
        docker {
          image 'node:16' // Use a Node.js image
        }
      }
      steps{
        sh 'npm install'
        sh 'npm test'
      }
    }

    stage("Build"){
      steps{
        sh 'npm run build'
      }
    }
  }
}