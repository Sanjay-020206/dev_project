pipeline {
    agent any
    tools {
        maven 'Maven 3' 
    }
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Sanjay-020206/dev_project.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t library-app:latest .'
            }
        }
    }
}
