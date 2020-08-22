pipeline {
    agent any
    tools {nodejs "node"}
    stages {
        stage('Cloning Git') {
            steps {
                git 'https://github.com/nilaprasad/Blogger-FullStack.git'
            }
        }
        stage('Test Client') {
            steps {
                dir('client') {
                  sh 'npm install'
                  sh 'npm start'
                }
            }
        }
        stage('Test') {
            steps {
                dir('server') {
                  sh 'npm install'
                  sh 'npm dev'
                }
            }
        }
  }
}
