pipeline {
    agent any
 
    stages {
        stage('Checkout') {
            steps {
                script {
                    git 'https://github.com/srezza/FAT.git'
                }
            }
        }
 
        stage('Build') {
            steps {
                script {
                    sh 'mvn clean install'
                }
            }
        }
 
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t helloworld .'
                }
            }
        }
 
        stage('Push Docker Image') {
            steps {
                script {
                    sh 'docker push sreeza/helloworld'
                }
            }
        }
    }
}
