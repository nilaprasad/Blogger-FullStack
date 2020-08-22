pipeline {
    agent any
    tools {nodejs "latest"}
    stages {
        stage('Cloning Git') {
            steps {
                git 'https://github.com/nilaprasad/Blogger-FullStack.git'
            }
        }
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test Client') {
            steps {
                sh 'npm  run start'
            }
        }
        stage('Test') {
            steps {
                sh 'npm  run start'
            }
        }
  }
}
