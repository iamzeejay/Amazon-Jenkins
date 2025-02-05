pipeline {
    agent any
    environment {
        PATH = "C:\\Program Files\\Git\\bin;C:\\Maven\\bin;C:\\Windows\\System32"
    }
    stages {
        stage('Clone Repository') {
            steps {
                // Cloning the repository from GitHub
                git branch: 'main', url: 'https://github.com/iamzeejay/Amazon-Jenkins.git'
            }
        }
        stage('Compile') {
            steps {
                // Running the Maven compile command
                bat 'set PATH=C:\Program Files\Java\apache-maven-3.9.9\bin;%PATH%'
                bat 'mvn compile'
            }
        }
        stage('Build') {
            steps {
                // Running the Maven clean install command
                bat 'set PATH=C:\Program Files\Java\apache-maven-3.9.9\bin;%PATH%'
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
