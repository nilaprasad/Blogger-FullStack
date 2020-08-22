pipeline {
  environment {
    dockerClientRegistry = "acdnilaprasad/blogger-frontend-dev"
    dockerServerRegistry = "acdnilaprasad/blogger-backend-dev"
    dockerRegistryCredential = 'dockerhub'
    dockerImage = ''
  }
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
        stage('Test Server') {
            steps {
                dir('server') {
                  sh 'npm install'
                  sh 'npm test'
                }
            }
        }
        stage('Build Client Image') {
            steps {
                dir('client') {
                  script {
                    dockerImage = docker.build dockerClientRegistry
                    docker.withRegistry ('', dockerRegistryCredential) {
                      dockerImage.push()
                    }
                  }
                }
            }
        }
        stage('Build Server Image') {
            steps {
                dir('server') {
                  script {
                    dockerImage = docker.build dockerServerRegistry
                    docker.withRegistry ('', dockerRegistryCredential) {
                      dockerImage.push()
                  }
                }
            }
        }
  }
}
