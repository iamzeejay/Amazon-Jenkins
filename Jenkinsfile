pipeline {
    agent any
    environment {
        PATH = "C:\\Program Files\\Git\\bin;C:\\Maven\\bin;C:\\Windows\\System32"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }
        stage('Compile') {
            steps {
                bat 'mvn compile'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }
    post {
        success {
            echo 'Build successful'
        }
        failure {
            echo 'Build failed'
        }
    }
}
