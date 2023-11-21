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
 
    post {
        failure {
            stage('Error Handling') {
                steps {
                    echo 'Pipeline failed! Check the logs for more details.'
                    // Additional error handling steps can be added here
                }
            }
        }
    }
}
