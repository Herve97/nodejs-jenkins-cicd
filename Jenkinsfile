pipeline {
  agent any
  stages{
    stage("checkout"){
      steps{
        checkout scm
      }
    }

    stage("test"){
      agent {
        docker {
          image 'node:20-alpine' // Use a Node.js image
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