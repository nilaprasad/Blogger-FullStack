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
                dir('var/lib/jenkins/workspace/blogger/client/')
                sh 'npm start'
            }
        }
        stage('Test') {
            steps {
              dir('var/lib/jenkins/workspace/blogger/server/')
                sh 'npm dev'
            }
        }
  }
}
