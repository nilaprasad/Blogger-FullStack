pipeline {
    agent any
    tools {nodejs "node"}
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
                dir('./client/')
                sh 'npm start'
            }
        }
        stage('Test') {
            steps {
              dir('./server')
                sh 'npm dev'
            }
        }
  }
}
