pipeline {
  agent any
  tools { nodejs "node" }
  stages {
    stage('Cloning Git') {
      steps {
        git "https://github.com/nilaprasad/Blogger-FullStack"
      }
    }
    stage('Install Packages') {
       steps {
         sh 'npm install'
       }
    }
    stage('Test Client') {
      steps {
        sh 'npm run start'
      }
    stage('Test Server') {
      steps {
        sh 'npm run dev'
      }
    }
  }
}

