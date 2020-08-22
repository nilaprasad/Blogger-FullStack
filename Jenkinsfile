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
                sh 'pwd'
                dir('client')
                sh 'npm install'
                sh 'npm start'
            }
        }
        stage('Test') {
            steps {
                sh 'pwd'
                dir('server')
                sh 'npm install'
                sh 'npm dev'
            }
        }
  }
}
