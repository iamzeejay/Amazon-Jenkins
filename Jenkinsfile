pipeline {
    agent any

    environment {
        PATH = "C:\\Program Files\\Git\\bin;C:\\Program Files\\Java\\apache-maven-3.9.9\\bin;C:\\Windows\\System32"
    }

    tools {
        maven 'Default Maven'  // Jenkins global tool configuration name
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/iamzeejay/Amazon-Jenkins.git'
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

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv() {
                    bat 'mvn clean verify sonar:sonar -Dsonar.projectKey=test -Dsonar.projectName=test'
                }
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
