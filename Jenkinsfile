pipeline {
    agent any
    stages {
        stage('SCM Checkou') {
            steps {
                git 'https://github.com/bivaswap/python_hello_world'
            }
        }
        stege('Build Image') {
            steps {
                script {
                    dockerImage = docker.build registery + ":$BUILD_NUMBER"
                }
            }
        }
        stage('Push Image') {
            steps {
                docker.withRegistry( "" ){
                    dockerImage.push()
                }
            }
        }
    }
}