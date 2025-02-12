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